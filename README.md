<div align="center">

## Simple SWING Example Very Helpful, For Me Anyway\.


</div>

### Description

This little thingy here just demonstrates the very primitive use of SWING!!!!!!!!!!!!!!!!!!!!!!!!!
 
### More Info
 
Sticky fingers.


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[C\.V\.](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/c-v.md)
**Level**          |Beginner
**User Rating**    |4.8 (19 globes from 4 users)
**Compatibility**  |Java \(JDK 1\.1\), Java \(JDK 1\.2\)
**Category**       |[Windows](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/windows__2-80.md)
**World**          |[Java](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/java.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/c-v-simple-swing-example-very-helpful-for-me-anyway__2-3907/archive/master.zip)





### Source Code

```
import java.awt.*;
import java.awt.event.*;
import javax.swing.*;
import javax.swing.event.*;
public class Swing1 extends JFrame implements DocumentListener, ActionListener {
  public Swing1() {
    //Set attributes of the frame
    setTitle("SWING Sample One");
    setSize(600, 400);
    setResizable(true);
    setLocation(100, 100);
    //Define the container for all of the controls and the main panel(s)
    Container contentPane = getContentPane();
    JPanel panel1 = new JPanel(null);
    //Define the components of the held within the frame and panel(s)
    text1 = new JTextField("", 10);
    button1 = new JButton("Set");
    button2 = new JButton("Get");
    text1.setBounds(20, 20, 80, 20);
    panel1.add(text1);
    button1.setBounds(120, 20, 80, 20);
    panel1.add(button1);
    button2.setBounds(220, 20, 80, 20);  //Defines the coordinates of the component Format=(x, y, w, h)
    panel1.add(button2);  //Adds the component to the panel
    //Add the ActionListeners for the components
    text1.addKeyListener(new java.awt.event.KeyAdapter() {
      public void keyPressed(java.awt.event.KeyEvent evt) {
        System.out.println("Key pressed!");
      }
    });
    button1.addMouseListener(new javax.swing.event.MouseInputAdapter() {
      public void mouseReleased(java.awt.event.MouseEvent evt) {
        text1.setText("Tested");
      }
    });
    button2.addMouseListener(new javax.swing.event.MouseInputAdapter() {
      public void mouseReleased(java.awt.event.MouseEvent evt) {
        JOptionPane.showMessageDialog(null, text1.getText(), "text1 has the value of:", 1);
      }
    });
    //Define the menu and their items. Coded here in the heirarchy's visual format
    menuBar = new JMenuBar();
      mnuFile = new JMenu("File");
        mnuNew = new JMenuItem("New");
        mnuNew.addActionListener(new java.awt.event.ActionListener() {
          public void actionPerformed(java.awt.event.ActionEvent evt) {
            JOptionPane.showMessageDialog(null, mnuNew.getText(), "The item you selected is:", 1);
          }
        });
        mnuOpen = new JMenu("Open");
          mnuItem1 = new JMenuItem("Item 1");
          mnuItem2 = new JMenuItem("Item 2");
          mnuItem3 = new JMenuItem("Item 3");
          //Add the menu items
          mnuOpen.add(mnuItem1);
          mnuOpen.add(mnuItem2);
          mnuOpen.add(mnuItem3);
        mnuExit = new JMenuItem("Exit");
        mnuCheckBoxMenuItem = new JCheckBoxMenuItem("Check Box Menu Item");
        sepOne = new JSeparator();
        //Add the menu items
        mnuFile.add(mnuNew);
        mnuFile.add(mnuOpen);
        mnuFile.add(mnuCheckBoxMenuItem);
        mnuFile.add(sepOne);
        mnuFile.add(mnuExit);
    //Add the top-level menus to the menuBar
    menuBar.add(mnuFile);
    //Add the top-level components (i.e. Panels, MenuBar, etc...)
    contentPane.add(panel1);
    contentPane.add(menuBar, "North");
    //Monitor for the closing of the window
    addWindowListener(new WindowAdapter() {
      public void windowClosing(WindowEvent e) {
        System.exit(0);
      }
    });
  }
  public static void main(String[] args) {
    JFrame frame = new Swing1();
    frame.show();
  }
  public void actionPerformed(ActionEvent e) {}
  public void insertUpdate(DocumentEvent e) {}
  public void changedUpdate(DocumentEvent e) {}
  public void removeUpdate(DocumentEvent e) {}
  //Global declarations for all components used
  private JButton button1;
  private JButton button2;
  private JTextField text1;
  private JMenuBar menuBar;
  private JMenu mnuFile;
  private JMenuItem mnuNew;
  private JMenu mnuOpen;
  private JMenuItem mnuExit;
  private JMenuItem mnuItem1;
  private JMenuItem mnuItem2;
  private JMenuItem mnuItem3;
  private JCheckBoxMenuItem mnuCheckBoxMenuItem;
  private JSeparator sepOne;
}
```

