# cluminating20230529
Arithmetic Games
/*
 * Click nbfs://nbhost/SystemFileSystem/Templates/Licenses/license-default.txt to change this license
 * Click nbfs://nbhost/SystemFileSystem/Templates/Classes/Class.java to edit this template
 */
package final2023;

import java.awt.Color;
import java.awt.Font;
import java.awt.GridBagConstraints;
import java.awt.GridBagLayout;
import java.awt.event.ActionEvent;
import java.util.Random;
import javax.swing.JButton;
import javax.swing.JComboBox;
import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JPanel;
import javax.swing.JTextField;
import javax.swing.SwingUtilities;

/**
 *
 * @author y111e
 */

public class arithmeticgames{ 
    public static void main(String[] args){
                SwingUtilities.invokeLater(arithmeticgames::createAndShowGUI);
    }

private static void createAndShowGUI() {
JFrame frame = new JFrame("Arithmetic Game");
frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
frame.setSize(370, 300);
        
JPanel panel = new JPanel(new GridBagLayout());
GridBagConstraints c = new GridBagConstraints();
c.anchor = GridBagConstraints.WEST;
        
JPanel color = new JPanel();
panel.setBounds(40,70,100,100);
panel.setBackground(Color.PINK);

frame.add(panel);

JLabel levelselect = new JLabel("SELECT LEVEL:");
        c.gridx = 0;
        c.gridy = 0;
        panel.add(levelselect, c);        

JComboBox<String> levelselectComboBox = new JComboBox<>(new String[]{"EASY","REGULAR","HARD"});
        c.gridy = 0;
        c.gridx = 1;
        panel.add(levelselectComboBox, c);

c.gridy = 1;
        panel.add(new JLabel(" "), c);
        
JButton nextButton = new JButton("NEXT");
        c.anchor = GridBagConstraints.CENTER;
        c.gridy = 2;
        c.gridx = 1;
        panel.add(nextButton, c);  
        
JLabel num1Label = new JLabel("num1");
        c.gridy = 2;
        c.gridx = 2;
        panel.add(num1Label, c);   
        
        Font font = num1Label.getFont();
        Font biggerFont = font.deriveFont(font.getSize() + 5f); // Increase the font size
        num1Label.setFont(biggerFont);
        
        nextButton.addActionListener((ActionEvent e) -> {
        String selectedOption = (String) levelselectComboBox.getSelectedItem();
                
        if(selectedOption.equals("EASY")){ 
            Random easyr1 = new Random();
            int i = easyr1.nextInt(10);
            num1Label.setText(String.valueOf(i));}
        
        else if(selectedOption.equals("REGULAR")){ 
            Random regularr1 = new Random();
            int ii = regularr1.nextInt(100);
            num1Label.setText(String.valueOf(ii));}
                
        else if (selectedOption.equals("HARD")) { 
            Random hardr1 = new Random();
            int iii = hardr1.nextInt(1000);
            num1Label.setText(String.valueOf(iii));
        }
        });

                           
JLabel add = new JLabel("+");
        c.gridy = 2;
        c.gridx = 3;
        panel.add(add, c); 
        
        Font font1 = add.getFont();
        Font biggerFont1 = font1.deriveFont(font.getSize() + 5f); // Increase the font size
        add.setFont(biggerFont1);
        
JLabel num2Label = new JLabel("num2");
        c.gridy = 2;
        c.gridx = 4;
        panel.add(num2Label, c); 
        
        Font font2 = num2Label.getFont();
        Font biggerFont2 = font2.deriveFont(font.getSize() + 5f); // Increase the font size
        num2Label.setFont(biggerFont2);
        
        nextButton.addActionListener((ActionEvent e)-> {
             String selectedOption = (String) levelselectComboBox.getSelectedItem();
        
        if(selectedOption.equals("EASY")){ 
            Random easyr2 = new Random();
            int i = easyr2.nextInt(10);
                num2Label.setText(String.valueOf(i));}
        
        else if (selectedOption.equals("REGULAR")){
            Random regularr2 = new Random();
            int ii = regularr2.nextInt(100);
            num2Label.setText(String.valueOf(ii));}
        
        else if (selectedOption.equals("HARD")) {
            Random hardr2 = new Random();
            int iii = hardr2.nextInt(1000);
            num2Label.setText(String.valueOf(iii));
           }
           
        });
        
c.gridy = 3;
        panel.add(new JLabel(" "), c);
         
JLabel resultLabel = new JLabel("YOUR ANSWER:");
        c.anchor = GridBagConstraints.WEST;
        c.gridy = 4;
        c.gridx = 0;
        panel.add(resultLabel, c);

JTextField textField = new JTextField(8);
        c.anchor = GridBagConstraints.WEST;
        c.gridy = 4;
        c.gridx = 1;
        panel.add(textField, c);
        
JLabel hintLabel = new JLabel("*enter the number ; )");
        c.anchor = GridBagConstraints.WEST;
        c.gridy = 5;
        c.ipadx = 1;
        panel.add(hintLabel, c);    

c.gridy = 6;
        panel.add(new JLabel(" "), c);          
        
JButton judgeButton = new JButton("JUDGE");
        c.anchor = GridBagConstraints.CENTER;
        c.gridy = 7;
        c.gridx = 1;
        panel.add(judgeButton, c);  
        
JLabel resultofLabel = new JLabel();
        c.anchor = GridBagConstraints.WEST;
        c.gridy = 8;
        c.gridx = 0;
        panel.add(resultofLabel, c);
      
judgeButton.addActionListener((ActionEvent e) -> {
        int number1 = Integer.parseInt(num1Label.getText());
        int number2 = Integer.parseInt(num2Label.getText());
        int sumresult = Integer.parseInt(textField.getText());
        int sum = number1 + number2;
        boolean judgeresult = sum == sumresult;         
        resultofLabel.setText("RESULT: "+judgeresult);                 
});

  frame.add(panel);
         frame.setVisible(true);
         }
}
