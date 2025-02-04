# deck_cards
import java.util.ArrayList;
import java.util.Collections;
import java.util.List;
import java.util.Random;

public class Main  {       
public class Deck{
    //atributos 
   private List<Card>deck; 
   
   //comstructor 
   public Deck(){
       deck = new ArrayList<>();
       String[] palos ={"treboles","corazones","espadas","diamantes"};
       String[] colores ={"Rojo","Negro"};
       String[] valores ={"2", "3", "4", "5", "6", "7", "8", "9", "10", "A", "J", "Q", "K"};
       
       for (String palo : palos){
           String color = palo.equals("corazones")|| palo.equals("diamante")? "Rojo" : "Negro";
           for (String valor :valores ){
               deck.add(new Card(palo,color,valor));
           }
       }
       }
   //metodos
       public void shuffle(){
           Collections.shuffle(deck);
           System.out.println("Se mezclo el deck");
   }
       public void head(){
           if(!deck.isEmpty()){
               Card card =deck.remove(0);
               System.out.println(card);
               System.out.println("quedan "+deck.size() +" cartas en el deck.");
           }
       }
       public void pick(){
           if (!deck.isEmpty()) {
               Random rand = new Random();
               int index =rand.nextInt(deck.size());
               Card card =deck.remove(index);
               System.out.println(card);
               System.out.println("Quedan " + deck.size() + " cartas en el deck.");
                       
           }
       }
       
       public void hand(){
           if (deck.size()>= 5){
               System.out.println("mano de 5  cartas:");
               for (int i=0; i<5; i++){
                   Card card= deck.remove(0);
                   System.out.println(card);
               }
               System.out.println("Quedan " + deck.size() + " cartas en el deck.");
           } else{
               System.out.println("No hay suficientes crtaen el deck");   
           }
       }
       public int GetDeckSize(){
           return deck.size();
       }
}
    
    public class Card {
    //atributos 
    private String palo;
    private String color;
    private String valor; 
    
    //constructor 
    public Card(String palo, String color, String valor){
        this.palo= palo;
        this.color= color;
        this.valor= valor;
    }
    
    //metodos
    public String get_palo(){
        return palo;
    }
     public String get_color(){
        return color;
    }
      public String get_valor(){
        return valor;
    }
      @Override 
    public String toString(){
       return palo + ", " + color +", " + valor;  
    } 
}
}

