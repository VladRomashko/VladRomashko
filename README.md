using System;
using System.Drawing;
using System.Windows.Forms;

namespace GraphicApp
{
    public partial class MainForm : Form
    {
        public MainForm()
        {
            InitializeComponent();
        }

        private void MainForm_Load(object sender, EventArgs e)
        {
            this.Text = "Головне вікно";
            pictureBox.Image = Properties.Resources.my_image; // Зображення має бути додане до ресурсів проекту
        }

        private void OkButton_Click(object sender, EventArgs e)
        {
            this.Close();
        }

        private void AboutButton_Click(object sender, EventArgs e)
        {
            AboutForm aboutForm = new AboutForm();
            aboutForm.ShowDialog();
        }
    }

    public partial class MainForm : Form
    {
        private PictureBox pictureBox;
        private Button okButton;
        private Button aboutButton;
        private System.ComponentModel.IContainer components = null;

        protected override void Dispose(bool disposing)
        {
            if (disposing && (components != null))
            {
                components.Dispose();
            }
            base.Dispose(disposing);
        }

        private void InitializeComponent()
        {
            this.pictureBox = new PictureBox();
            this.okButton = new Button();
            this.aboutButton = new Button();
            ((System.ComponentModel.ISupportInitialize)(this.pictureBox)).BeginInit();
            this.SuspendLayout();
            // 
            // pictureBox
            // 
            this.pictureBox.Image = null;
            this.pictureBox.Location = new Point(50, 50);
            this.pictureBox.Size = new Size(200, 200);
            this.pictureBox.SizeMode = PictureBoxSizeMode.StretchImage;
            this.pictureBox.BorderStyle = BorderStyle.FixedSingle;
            // 
            // okButton
            // 
            this.okButton.Location = new Point(50, 270);
            this.okButton.Size = new Size(75, 23);
            this.okButton.Text = "Ok";
            this.okButton.Click += new EventHandler(this.OkButton_Click);
            // 
            // aboutButton
            // 
            this.aboutButton.Location = new Point(175, 270);
            this.aboutButton.Size = new Size(75, 23);
            this.aboutButton.Text = "About";
            this.aboutButton.Click += new EventHandler(this.AboutButton_Click);
            // 
            // MainForm
            // 
            this.ClientSize = new Size(300, 350);
            this.Controls.Add(this.aboutButton);
            this.Controls.Add(this.okButton);
            this.Controls.Add(this.pictureBox);
            this.FormBorderStyle = FormBorderStyle.FixedSingle;
            this.MaximizeBox = false;
            this.StartPosition = FormStartPosition.CenterScreen;
            this.Load += new EventHandler(this.MainForm_Load);
            ((System.ComponentModel.ISupportInitialize)(this.pictureBox)).EndInit();
            this.ResumeLayout(false);
        }
    }

    public partial class AboutForm : Form
    {
        public AboutForm()
        {
            InitializeComponent();
        }

        private void AboutForm_Load(object sender, EventArgs e)
        {
            this.Text = "About";
            AboutLabel.Text = "Прізвище, Ім’я студента\nГрупа: [номер групи]\nНомер варіанту: [номер варіанту]";
            AboutLabel.TextAlign = ContentAlignment.MiddleCenter;
        }
    }

    public partial class AboutForm : Form
    {
        private Label AboutLabel;
        private System.ComponentModel.IContainer components = null;

        protected override void Dispose(bool disposing)
        {
            if (disposing && (components != null))
            {
                components.Dispose();
            }
            base.Dispose(disposing);
        }

        private void InitializeComponent()
        {
            this.AboutLabel = new Label();
            this.SuspendLayout();
            // 
            // AboutLabel
            // 
            this.AboutLabel.AutoSize = true;
            this.AboutLabel.Location = new Point(50, 50);
            this.AboutLabel.Size = new Size(200, 100);
            // 
            // AboutForm
            // 
            this.ClientSize = new Size(300, 200);
            this.Controls.Add(this.AboutLabel);
            this.FormBorderStyle = FormBorderStyle.FixedSingle;
            this.MaximizeBox = false;
            this.StartPosition = FormStartPosition.CenterScreen;
            this.Load += new EventHandler(this.AboutForm_Load);
            this.ResumeLayout(false);
            this.PerformLayout();
        }
    }
}
