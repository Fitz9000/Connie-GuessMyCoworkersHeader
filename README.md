Sub GuessMyCoworkersHeader()

    'Enter your guesses here
    GuessTheHeader "Froot", "Fruut", "Fruit"

End Sub

Sub GuessTheHeader(g1, Optional g2 = "", Optional g3 = "", Optional g4 = "", Optional g5 = "", _
Optional g6 = "", Optional g7 = "", Optional g8 = "", Optional g9 = "", Optional g10 As String = "")

    Dim colOrder As Variant
    Dim col As Integer
    Dim search As Range
    Dim index As Integer
        
    colOrder = Array(g1, g2, g3, g4, g5, g6, g7, g8, g9, g10)
    col = 1
    
    For index = LBound(colOrder) To UBound(colOrder)
        Set search = Rows("1:1").Find(colOrder(index), LookIn:=xlValues, LookAt:=xlWhole, _
            SearchOrder:=xlByColumns, SearchDirection:=xlNext, MatchCase:=False)
        If Not search Is Nothing Then
            MsgBox "The header for this column is """ & search & """"
            Exit Sub
        End If
    Next index

End Sub
