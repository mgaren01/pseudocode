START

//Begin Program

INIT()

Patron.Input(A)
CP.receiveInput(A)

CP.checkItem

if(Database.confirmItem = true)
    Roboarm.travelTo (Location)

if(Roboarm.checkLocation = true)
    if(Roboarm.checkDimensions)
        Roboarm.gripItem

Roboarm.travelTo (Patron)
Roboarm.releaseItem

//End Program

//Define Objects, Functions

Patron
    provides Input
    receives Item

INIT function
    CREATE CP (Central Processor)
    CREATE Database
    CREATE Input
    CREATE Roboarm
    CREATE Patron
    CREATE Item(s)
    CREATE Bookshelves (Product Map)

CP
    INIT
        Set variables
            patronInput
        
        receiveInput
        checkItem

Database
    INIT
        Set variables
            patronInput
            item () true/false
            itemLocation
            itemDimensions

Roboarm
    INIT
        Set variables
            patronInput
            itemLocation
            itemDimensions

        travelTo (Location/Patron)
        checkLocation
        checkDimensions
        gripItem
        releaseItem

END