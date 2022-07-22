---
layout: post
title:  "[Unity] Cursor size with new Input System"
---

# [Unity] Cursor size with new Input System

When using the **Input Manager**, changing the texture of the cursor can change its size.

When I replaced the **Input Manager** with the current **Input System**, I encountered a problem with the inability to scale the cursor.

That is why I offer you a simple solution to this problem, which allows you to get a wider range of opportunities to interact with the cursor.

 1. Create a new **Canvas**.
 2. Create a new **GameObject** with the **Image** component on it as a child of the created canvas.
 3. Attach the following script to the created object
 4. Assign your cursor sprite to the Image component.

```cs
using UnityEngine;
using UnityEngine.InputSystem;

public class CustomCursor : MonoBehaviour
{
	public RectTransform mCanvas;
    public RectTransform mCursorVisual;
    public Vector2 mDisplacement = new Vector2(8,-8);

    private Vector2 _mousePos;
    private Vector2 _mousePosEqu;
    private Vector2 _realPos;
    
    public bool visible
    {
        set => mCursorVisual.gameObject.SetActive(value);
    }
       
    void LateUpdate()
    {
        _mousePos = Mouse.current.position.ReadValue();
        _mousePosEqu = new Vector2(_mousePos.x/Screen.width,   _mousePos.y/Screen.height);
        _realPos = new Vector2(mCanvas.rect.width * _mousePosEqu.x, mCanvas.rect.height * _mousePosEqu.y);
        
        mCursorVisual.anchoredPosition = _realPos + mDisplacement;
    }
}
 ```

 5. Assign to the **mCanvas** variable RectTransform of the **Canvas** you created earlier
6. Assign to the **mCursorVisual** variable RectTransform of the previously created **GameObject** with the Image component

*In my case, the mDisplacement variable has values (8,-8) because my cursor is 16 by 16 pixels and I need to set it to shift so that the corner of the Image Cursor is where the cursor actually is.*

As you can see, this implementation contains a feature:
CustomCursor.visible
Available when using the standard cursor
Cursor.visible

I hope someone will find this solution useful.
Thank you for your attention.

