# Calculator
My first java project using swing 
import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JTextField;

import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
public class Calculator extends JFrame implements ActionListener {
   Container c;
   JLabel label1,label2,label3;
   JTextField t1,t2;
   JButton plus,minus,mul,div,clear;
   public Calculator()
   {
    setTitle("Calculator");
    setSize(600, 600);
    setLocationRelativeTo(null);
    // setLocation(100,100);
    setDefaultCloseOperation(EXIT_ON_CLOSE);
     setResizable(false);
    c=this.getContentPane();
    c.setLayout(null);

    label1 =new JLabel("Enter first number:");
    label1.setBounds(50,40,170,20);
    label1.setFont(new Font("Ariel", Font.BOLD, 18));
    c.add(label1);

    label2 =new JLabel("Enter second number:");
    label2.setBounds(50,85,200,20);
    label2.setFont(new Font("Ariel", Font.BOLD, 18));
    c.add(label2);

    label3 =new JLabel("result : ");
    label3.setBounds(45,220,250,20);
    label3.setFont(new Font("Ariel", Font.BOLD, 18));
    c.add(label3);

    t1=new JTextField();
    t1.setBounds(300,35,100,30);
    t1.setFont(new Font("Ariel", Font.BOLD, 18));
    c.add(t1);

    t2=new JTextField();
    t2.setBounds(300,80,100,30);
    t2.setFont(new Font("Ariel", Font.BOLD, 18));
    c.add(t2);

    plus=new JButton("+");
    plus.setBounds(40,160,50,30);
    plus.setFont(new Font("Ariel",Font.BOLD,20));
    c.add(plus);

    minus=new JButton("-");
    minus.setBounds(120,160,50,30);
    minus.setFont(new Font("Ariel",Font.BOLD,20));
    c.add(minus);

    mul=new JButton("X");
    mul.setBounds(200,160,50,30);
    mul.setFont(new Font("Ariel",Font.BOLD,20));
    c.add(mul);

    div=new JButton("/");
    div.setBounds(290,160,50,30);
    div.setFont(new Font("Ariel",Font.BOLD,20));
    c.add(div);

    clear=new JButton("C");
    clear.setBounds(390,160,50,30);
    clear.setFont(new Font("Ariel",Font.BOLD,20));
    c.add(clear);

    plus.addActionListener(this);
    minus.addActionListener(this);
    div.addActionListener(this);
    mul.addActionListener(this);
    clear.addActionListener(this);
    setVisible(true);
   
   } 
    public void actionPerformed(ActionEvent e)
    {
        try{
            if(e.getSource()==plus)
        {
         int a=Integer.parseInt(t1.getText());
         int b=Integer.parseInt(t2.getText());
          int c=a+b;
          label3.setText(a+"+ "+b+" = "+c);  
        }
        if(e.getSource()==minus)
        {
         int a=Integer.parseInt(t1.getText());
         int b=Integer.parseInt(t2.getText());
          int c=a-b;
          label3.setText(a+" - "+b+" = "+c);  
        }
        if(e.getSource()==mul)
        {
         int a=Integer.parseInt(t1.getText());
         int b=Integer.parseInt(t2.getText());
          int c=a*b;
          label3.setText(a+" X "+b+" = "+c);  
        }
        if(e.getSource()==div)
        {
         int a=Integer.parseInt(t1.getText());
         int b=Integer.parseInt(t2.getText());
         
            int c=a/b;
            label3.setText(a+ " / "+b+" = "+c);
        }
        if(e.getSource()==clear)
        {
            t1.setText(null);
            t2.setText(null);
        }
    }
    catch(NumberFormatException n)
    {
       label3.setText("Enter integer values only");
    }
    catch(ArithmeticException t)
    {
        label3.setText("cannot divide by zero");
    }
    }

    
   public static void main(String[] args) {
    Calculator cl=new Calculator();

    
   }
}
