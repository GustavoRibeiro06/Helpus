# Helpus
Abra o  BlueJ e crie uma GUI para  login no Sistema XPTO. A GUI deve conter: JLabel 1: Para entrar no sistema XPTO, digite seu nome e senha: JLabel 2: Nome: JTextField para inserção do nome. JLabel 3: Senha: JPasswordField para inserção da senha O tratamento de eventos deve retornar a mensagem “Obrigado por digitar seu  nome” quando o usuário pressionar “ enter ” após preencher o campo “nome” e  retornar a mensagem “Obrigado por preencher sua senha!” após preencher o  campo “senha”. Finalmente, crie uma classe de teste para sua GUI

import javax.swing.JLabel;

import java.awt.FlowLayout;

import java.awt.event.ActionListener;

import java.awt.event.ActionEvent;

import javax.swing.JFrame;

import javax.swing.JTextField;

import javax.swing.JPasswordField;

import javax.swing.JOptionPane;


public class LabelFrame extends JFrame {
    
    private final JLabel label1;
    private final JLabel label2;
    private final JTextField textField1;
    private final JPasswordField passwordField;
    private final JLabel label3;
    
    
    public LabelFrame (){
        super ("XPTO");
        setLayout (new FlowLayout());
        
        
        label3 = new JLabel ("Para entrar no sistema XPTO, digite seu nome e senha");
        label3.setToolTipText ("D");
        add (label3);
        
        
        label1 = new JLabel ("nome");
        label1.setToolTipText ("D");
        add (label1);
        
        
        textField1 = new JTextField (10);
        label1.setToolTipText ("Digite");
        add (textField1);
        
        
        label2 = new JLabel ("Senha");
        label2.setToolTipText ("D");
        add (label2);
        
        
        passwordField = new JPasswordField ("Hidden text");
        add (passwordField);
        
      LabelFrameHandler handler = new LabelFrameHandler();
      label3.addActionListener(handler); - Erro
      label1.addActionListener(handler); - Erro
      label2.addActionListener(handler); - Erro
      passwordField.addActionListener(handler);
    }

    private class LabelFrameHandler implements ActionListener 
   {
      
      @Override
      public void actionPerformed(ActionEvent event)
      {
         String string = ""; 
         if (event.getSource() == label3)
            string = String.format("bem vindo ao sistema",
               event.getActionCommand());

         else if (event.getSource() == label1)
            string = String.format("textField2: %s",
               event.getActionCommand());

         else if (event.getSource() == label2)
            string = String.format("textField3: %s", 
               event.getActionCommand());

         else if (event.getSource() == passwordField)
            string = String.format("passwordField: %s", 
               event.getActionCommand());

         JOptionPane.showMessageDialog(null, string); 
      } 
   } 
}

-----------------------------------------------------------------------------------

Segunda CLasse 

import javax.swing.JFrame;

public class TextFieldTest

{

   public static void main(String[] args)
   
   { 
   
      LabelFrame textFieldFrame = new LabelFrame(); 
      
      textFieldFrame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
      
      textFieldFrame.setSize(350, 100); 
      
      textFieldFrame.setVisible(true); 
   } 
} 
