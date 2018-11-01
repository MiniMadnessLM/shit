
;Yo, quick and simple click sleep loop cycle
;commands:
;W = Reloads the program from the start
;E = Closes the program
;Right Mouse Button = selects click point, then input box with delay in milliseconds
;S = asks how many loops you want to do, then does it
;P = Pauses the program (don't think this works though so just hit E)


CoordMode, Mouse, Screen

a := 0
b := 0
c := 0

W::
	Reload
Return

E::
	ExitApp
Return

RButton::
	MouseGetPos, x, y
	x%a% := x
	y%a% := y
	InputBox, s, Sleep, (1000 = 1s)
	s%a% := s
	a++
Return

S::
	InputBox, r, How many loops?
	While c != r
	{
		While b != a
		{
				xx := x%b%
				yy := y%b%
				ss := s%b%
				Click, %xx%, %yy% Left, 1
				Sleep, %ss%
				b++
		}
		b := 0
	c++
	}
b := 0
c := 0
Return

P::
	Pause
Return

