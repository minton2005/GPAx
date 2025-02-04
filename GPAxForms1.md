namespace WinFormsApp1
{
    public partial class Form1 : Form
    {
        private List<double> gpaxList = new List<double>();
        private GPACalculator calculator = new GPACalculator();
        public Form1()
        {
            InitializeComponent();
        }

        private void button1_Click(object sender, EventArgs e)
        {
            try
            {
                double gpax = double.Parse(tbGPAx.Text);
                gpaxList.Add(gpax);
                calculator.AddGPAX(gpax);

                UpdateDisplay();
                tbGPAx.Clear();
            }
            catch (FormatException)
            {
                MessageBox.Show("please enter a valid GPAX ", "Error", MessageBoxButtons.OK, MessageBoxIcon.Error);
            }
            catch (OverflowException)
            {
                MessageBox.Show("GPAX must be between 0 and 4.", "Error", MessageBoxButtons.OK, MessageBoxIcon.Error);
            }
        }

        private void UpdateDisplay()
        {
            tbGPAx.Text = calculator.CalculateAverageGPAX().ToString("0.00");
            tbCount.Text = calculator.GetCount().ToString();
            tbMax.Text = calculator.GetMaxGPAX().ToString("0.00");
            tbMin.Text = calculator.GetMinGPAX().ToString("0.00");
        }
    }
}

