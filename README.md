<div align="center">

## Code for a basic Pong style game\!


</div>

### Description

Makes a little pong style game
 
### More Info
 
Nothin much, just a very basic knowledge of VB programming.


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Matthew Eagar](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/matthew-eagar.md)
**Level**          |Unknown
**User Rating**    |4.5 (18 globes from 4 users)
**Compatibility**  |VB 3\.0, VB 4\.0 \(16\-bit\), VB 4\.0 \(32\-bit\), VB 5\.0, VB 6\.0
**Category**       |[Games](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/games__1-38.md)
**World**          |[Visual Basic](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/visual-basic.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/matthew-eagar-code-for-a-basic-pong-style-game__1-1971/archive/master.zip)





### Source Code

```
Dim vmom As Integer 'holds the ball's vertical momentum
Dim hmom As Integer 'holds the ball's horizontal momentum
Private Sub Form_Load()
  Randomize
  'make the vertical and horizontal momentums random
  vmom = 100 + Int(Rnd * 200)
  hmom = 100 + Int(Rnd * 200)
End Sub
Private Sub Form_MouseMove(Button As Integer, Shift As Integer, X As Single, Y As Single)
  'move the paddle to the mouse's position
  Shape1.Left = X - (Shape1.Width / 2)
End Sub
Private Sub Timer1_Timer()
  'move the ball, based on the virtical and horizontal momenutm
  Shape2.Top = Shape2.Top + vmom
  Shape2.Left = Shape2.Left + hmom
  'see if the ball is hitting the surface of the paddle
 If (Shape2.Top + Shape2.Height) > Shape1.Top Then
    If Shape2.Left + Shape2.Width >= Shape1.Left And Shape2.Left <= Shape1.Left + Shape1.Width Then
    vmom = -vmom
  End If
End If
'see if the ball has hit the edge of the screen
If (Shape2.Left + Shape2.Width) > Form1.Width Then
  Shape2.Left = Form1.Width - Shape2.Width
  hmom = -hmom 'this reverses it ball's direction
ElseIf Shape2.Left < 0 Then
  Shape2.Left = 0
  hmom = -hmom 'this reverses it ball's direction
ElseIf Shape2.Top < 0 Then
  Shape2.Top = 0
  vmom = -vmom 'this reverses it ball's direction
ElseIf Shape2.Top > Form1.Height Then
  MsgBox "You lost!"
  Timer1.Enabled = False
End If
End Sub
```

