
import java.io.FileNotFoundException;

import java.util.Scanner;

public class Main
{

public static void main(String args[]) throws FileNotFoundException{

boolean gameRunning = true;

PlayerData currentPlayer = new PlayerData();

currentPlayer = Login.menu();

while(gameRunning == true){

System.out.println("What would you like to do?");

System.out.println("1 : Battle");

System.out.println("2 : Shop");

System.out.println("3 : Save");

System.out.println("4 : Quit Game");

Scanner command = new Scanner(System.in);

int currentCommand = command.nextInt();

if(currentCommand == 1){

Battle battle = new Battle(currentPlayer);

battle.setEnemyTroops();

battle.setPlayerTroops();
                
                while(battle.checkFinished() != "Player won!" || battle.checkFinished() != "Enemy won!"){
                    battle.printBattleField();
                    System.out.println("What would you like to do?");
                    System.out.println("1 : Move");
                    System.out.println("2 : Attack");
                    System.out.println("3 : End Turn");
                    int battleCommand = command.nextInt();
                    if(battleCommand == 1){
                        System.out.println("Select a troop to move");
                        System.out.println("x :");
                        int x = command.nextInt();
                        System.out.println("y :");
                        int y = command.nextInt();
                        //battle.printBattleField();
                        Troops selectedUnit = battle.selectUnit(x, y);
                        selectedUnit.gamePlayPrint();
                        System.out.println("Type Q to cancel anything else to continue. ");
                        String cancel = command.next();
                        if(cancel.equals("q") || cancel.equals("Q")){
                            continue ;
                        }
                        System.out.println("Move unit to");
                        System.out.println("x :");
                        x = command.nextInt();
                        System.out.println("y :");
                        y = command.nextInt();
                        battle.move(x, y, selectedUnit);
                    }
                    else if(battleCommand == 2){
                        System.out.println("Select a troop to use");
                        System.out.println("x :");
                        int x = command.nextInt();
                        System.out.println("y :");
                        int y = command.nextInt();
                        Troops selectedUnit = battle.selectUnit(x, y);
                        selectedUnit.gamePlayPrint();
                        System.out.println("Type Q to cancel anything else to continue. ");
                        String cancel = command.next();
                        if(cancel.equals("q") || cancel.equals("Q")){
                            continue ;
                        }
                        System.out.println("Attack unit at");
                        System.out.println("x :");
                        x = command.nextInt();
                        System.out.println("y :");
                        y = command.nextInt();
                        Troops selectedEnemyUnit = battle.selectUnit(x, y);
                        selectedEnemyUnit.gamePlayPrint();
                        System.out.println("Type Q to cancel anything else to continue. ");
                        cancel = command.next();
                        if(cancel.equals("q") || cancel.equals("Q")){
                            continue ;
                        }
                        battle.attack(x, y, selectedUnit);
                        selectedEnemyUnit.gamePlayPrint();
                    }
                    else if(battleCommand == 3){
                        battle.endTurn();
                    }
                    else{
                        System.out.println("Please enter a valid command");
                    }
                }
            }
            if(currentCommand == 2){
                currentPlayer = Shop.shopWindow(currentPlayer);
            }
            if(currentCommand == 3){
                Login.saveData(currentPlayer);
            }
            if(currentCommand == 4){
                gameRunning = false;
            }
            else{
                System.out.println("Please enter a valid command");
            }
        }
    }
}
