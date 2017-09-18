using System;
using System.Collections.Generic;
using System.ComponentModel;
using System.Data;
using System.Drawing;
using System.Linq;
using System.Text;
using System.Threading.Tasks;
using System.Windows.Forms;
using static System.Windows.Forms.VisualStyles.VisualStyleElement.Button;

namespace SE_HW_1
{
    public partial class Form1 : Form
    { 

        public Form1()
        {
            InitializeComponent();
        }

        public static string ConvertToUpperCase(string str)
        {

            if (str == null)
            {
                return null;
            }

            int i = 0;
            int j = str.Length - 1;
            StringBuilder sb;

            while (i < str.Length)
            {
                if (Char.IsWhiteSpace(str[i]))
                {
                    i++;
                }
                else
                {
                    break;
                }
            }

            while (j > i)
            {
                if (Char.IsWhiteSpace(str[j]))
                {
                    j--;
                }
                else
                {
                    break;
                }
            }

            if (i > j)
            {
                return "";
            }

            sb = new StringBuilder(j - i + 1);

            while (i <= j)
            {

                sb.Append(Char.ToUpper(str[i]));
                i++;
            }
            return sb.ToString();
        }
        static public string TrimAndLower(string str)
        {
            if (str == null)
            {
                return null;
            }
            int i = 0;
            int j = str.Length - 1;
            StringBuilder sb;

            while (i < str.Length)
            {
                if (Char.IsWhiteSpace(str[i])) 
                {
                    i++;
                }
                else
                {
                    break;
                }
            }

            while (j > i)
            {
                if (Char.IsWhiteSpace(str[j])) 
                {
                    j--;
                }
                else
                {
                    break;
                }
            }
            if (i > j)
            {
                return "";
            }

            sb = new StringBuilder(j - i + 1);
            while (i <= j)
            {
                
                sb.Append(Char.ToLower(str[i]));
                i++;
            }
            return sb.ToString();
        }
        private void button1_Click(object sender, EventArgs e)
        {
            textBox2.Text = ConvertToUpperCase(textBox1.Text);
        }

        private void button2_Click(object sender, EventArgs e)
        {
            textBox2.Text = TrimAndLower(textBox1.Text);
        }
        private void button3_Click(object sender, EventArgs e)
        {
            string strInput = default(string);
            strInput = textBox1.Text;
            string[] strSplit = null;
            strSplit = strInput.Split(' ');
            textBox2.Text=("Number of words: " + strSplit.Length);
        }
        private void button4_Click(object sender, EventArgs e)
        {
            string strInput = default(string);
            strInput = textBox1.Text;
            textBox2.Text =("Number of Characters: "+ strInput.Length.ToString());
        }
        private void Form1_Load(object sender, EventArgs e)
        {
        }
        private void textBox1_TextChanged(object sender, EventArgs e)
        {
        }
    }
