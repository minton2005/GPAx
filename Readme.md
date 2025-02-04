@startuml
class Form1 {
    - gpaxList : List<double>
    - calculator : GPACalculator
    + Form1()
    - button1_Click(object sender, EventArgs e) : void
    - UpdateDisplay() : void
}

class GPACalculator {
    - gpaxList : List<double>
    + AddGPAX(double gpax) : void
    + CalculateAverageGPAX() : double
    + GetCount() : int
    + GetMaxGPAX() : double
    + GetMinGPAX() : double
}

Form1 -- GPACalculator : uses

@enduml