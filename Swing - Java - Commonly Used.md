## Center a Window
```java
//import java.awt.Dimension;
//import java.awt.Toolkit;

Dimension dimension = Toolkit.getDefaultToolkit().getScreenSize();
int x = (int) ((dimension.getWidth() - frame.getWidth()) / 2);
int y = (int) ((dimension.getHeight() - frame.getHeight()) / 2);
frame.setLocation(x, y);
```

## Control action using Timer
```java
//import javax.swing.Timer;

Timer timer = new Timer(5000, e -> {
        //action to be performed once the timer ends
        splashScreen.setVisible(false);
    }
);
timer.setRepeats(false);
timer.start();
```

## Override the Close(X) button of a window
```java
addWindowListener(new java.awt.event.WindowAdapter() {
    @Override
    public void windowClosing(java.awt.event.WindowEvent windowEvent) {
        //action to be performed if the Close(X) button is clicked.
        System.out.println("Close button is clicked!");
    }
});
```

## Action Listener

### If ActionListener interface is implemented
```java
//import java.awt.event.ActionEvent;
//import java.awt.event.ActionListener;

submitButton.addActionListener(this); //this refers to the instance of Listener.

public void actionPerformed(ActionEvent event){
    //action to be performed
    System.out.println("Submit Button is clicked");        
}
```

### Using Anonymous class to implement ActionListener
```java
//import java.awt.event.ActionEvent;
//import java.awt.event.ActionListener;

summitButton.addActionListener(new ActionListener(){
    public void actionPerformed(ActionEvent event){
        //action to be performed
        System.out.println("Submit Button is clicked");
    }
})
```

## Focus Actions - FocusListener
```java
messageTextField.addFocusListener(new FocusListener() {
    public void focusGained(FocusEvent e) {
        messageTextField.setText("");
    }

    public void focusLost(FocusEvent e) {
        messageTextField.setText("Type a message");
    }
});
```