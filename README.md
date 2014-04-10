# Emacs octicons glyph name

The octicon font provided by github (https://github.com/styleguide/css/7.0)
provides some nice icons embedded in a font. The strings below give an
easier access to them and must be used with the relevant face (octicons).

## Example

This define a mode-line that prepend an octoface (github) if the file is
under a version control system

```
(setq-default mode-line-format (list
   " "
   '(:eval (if (vc-backend buffer-file-name)
               (list
                (propertize octicon-octoface 'face 'octicons)
                (propertize " " 'face 'mode-line))))
   mode-line-mule-info
   'mode-line-modified
   "-  "
   'mode-line-buffer-identification
   "  (%l, %c)  "
   'mode-line-modes
   " -- "
   `(vc-mode vc-mode)
   ))
```