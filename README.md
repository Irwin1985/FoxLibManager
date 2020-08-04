# FoxLibManager
A VFP class for handling PRG based classes.

## How to use it
```
Just copy the FoxLibManager prg anywhere into your project PATH folder.
```

## Simple Test
```xBase

// suppose you have this PRG based class.

* Person.prg
Define Class clPerson As Custom
	_name = ""
	_last_name = ""
EndDefine

// declare the FoxLibManager Prg
Set Procedure to "FoxLibManager" Additive

// Instantiate FoxLibManager Object
FoxLib = CreateObject("FoxLibManager")

// Add Person class (pay attention to class name)
FoxLib.AddClass("clPerson")

// Add Person file
// remember file name could be different from class name.
FoxLib.AddProcedure("Person")

// Now load everything into memory
FoxLib.LoadProcedures()

// at this point you can call any routine or classes.
// included in your PRG file.
oPerson = CreateObject("clPerson")
oPerson._name = "John"
oPerson._last_name = "Doe"

// When finished just call ReleaseAll() procedure.
FoxLib.ReleaseAll()
```

## License

`FoxLibManager` is released under the MIT Licence.
