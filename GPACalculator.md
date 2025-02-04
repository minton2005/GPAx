using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Threading.Tasks;

namespace WinFormsApp1
{
    internal class GPACalculator
    {
        private List<double> gpaxList = new List<double>();

        public void AddGPAX(double gpax)
        {
            gpaxList.Add(gpax);
        }

        public double CalculateAverageGPAX()
        {
            if (gpaxList.Count == 0)
            {
                return 0;
            }
            return gpaxList.Average();
        }

        public int GetCount()
        {
            return gpaxList.Count;
        }

        public double GetMaxGPAX()
        {
            if (gpaxList.Count == 0)
            {
                return 0;
            }
            return gpaxList.Max();
        }

        public double GetMinGPAX()
        {
            if (gpaxList.Count == 0)
            {
                return 0;
            }
            return gpaxList.Min();
        }
    }

}