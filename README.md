# Refactoring

From Setthanat project(Typing Game): https://github.com/Ing140943/TypingGame

In PlayGame.java

```java
     /**
     * Check inout from user that they type correct characters or not.
     * @param let the character that they type.
     */
    public void checkLet (String let){
        if (let.charAt(0) != (currentString.charAt(positionNow))){
            drawWord(false);

        }
        else{
            positionNow++ ;
            drawWord(true);
            health = new Rectangle(100,300,30,val);
            if( positionNow == currentString.length()){
                getText();

            }
        }
    }
```


Rename the checkLet method name to checkLetter, checkLet make no sense.

       public void getText(){

        if (countWords == 100){
            showDialog();
            Main.window.show();
            gameStage.close();
        }

        health = new Rectangle(100,300,30,val);
        content.getChildren().clear();
        content.getChildren().addAll(wordsForTyping);
        health.setFill(GREEN);
        health.setTranslateX(260);
        health.setTranslateY(-30);

        positionNow = 0;
        currentString = getWords.getLabel();
        if ( currentString == null ){
            Main.window.show();
            gameStage.close();
        }
        else{
            countWords += 1;
            clock.stopTime();
            if (countWords <= 25 ){
                time = 7;
            }
            else if(countWords >= 45){
                time = 6;
            }
            else {
                time = 5;
            }
            clock = new TimerByMe(time);
            clock.setTranslateX(50);
            content.getChildren().addAll(clock,health);
            System.out.println("word : " + countWords);
            drawWord(true);
        }

 
    
in this method currentString == null can refactor to currentString.isBlank() 
and many many of if one line statement in this class can be written in one line if.
Ex. ```if (countWords <= 25 ){time = 7;}```
    
 
    


