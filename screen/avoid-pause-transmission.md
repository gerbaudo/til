# avoid pause transmission

If you are running screen, sometimes it will intercept the `Ctrl s`
(or the `Ctrl x s`) you are trying to send to emacs.

You can resume the frozen session with `Ctrl q`. But even better you can 
disable this "Pause transmission" feature of screen
- `Ctrl-a :flow off`: disable flow-control for this screen window
- `Ctrl-a :info`: check change

See also http://superuser.com/questions/251446/problem-with-gnu-screen-when-using-emacs-c-x-c-s-save-buffer
