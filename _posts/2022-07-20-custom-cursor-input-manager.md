

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

```cs
using UnityEngine;
using UnityEngine.InputSystem;

public class CustomCursor : MonoBehaviour
{
    public RectTransform mCursorVisual;
    public UnityEngine.UI.Image mImage;
    public Vector2 mDisplacement = new Vector2(8,-8);

    private Vector2 _mousePos;
    private Vector2 _mousePosEqu;
    private Vector2 _realPos;
    
    public bool visible
    {
        set => mCursorVisual.gameObject.SetActive(value);
    }
    
    public void SetCursor(Sprite cursor)
    {
        mImage.sprite = cursor;
    }
    
    void LateUpdate()
    {
        _mousePos = Mouse.current.position.ReadValue();
        _mousePosEqu = new Vector2(_mousePos.x/Screen.width,   _mousePos.y/Screen.height);
        _realPos = new Vector2(640 * _mousePosEqu.x, 360 * _mousePosEqu.y);
        
        mCursorVisual.anchoredPosition = _realPos + mDisplacement;
    }
}
 ```