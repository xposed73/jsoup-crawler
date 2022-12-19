
## JKBOSE Results Page
http://jkbose.nic.in/results/

```java
  public static void main(String[] args) throws IOException {
        // TODO code application logic here
        
        Document doc = Jsoup.connect("http://jkbose.nic.in/results/").get();
               
                Element table = doc.select("table").get(0); //select the first table.
                Elements rows = table.select("tr");

                for (int i = 1; i < rows.size(); i++) { //first row is the col names so skip it.
                    Element row = rows.get(i);
                    Elements cols = row.select("a");
                    
                    for (Element e : cols){
                        String title = e.text();
                        String url = e.absUrl("href");                        
                        System.out.println("NAME: " + title + "\nURL: " + url + "\n\n");                      
                    
                }
                
         }
    
}
```

https://jkbose.nic.in/DateSheets.html

```java
public static void main(String[] args) throws IOException {
       
        Document doc = Jsoup.connect("https://jkbose.nic.in/DateSheets.html").get();
               
                Element table = doc.select("table").get(0); //select the first table.
                Elements rows = table.select("tr");

                for (int i = 1; i < rows.size(); i++) { //first row is the col names so skip it.
                    Element row = rows.get(i);
                    Elements cols = row.select("a");
                    
                    for (Element e : cols){
                        String title = e.text();
                        String url = e.absUrl("href");                        
                        System.out.println("NAME: " + title + "\nURL: " + url + "\n\n");                      
                    }
                    
            }    
                
    }

```
```java

http://jkpsc.nic.in/

public class JavaApplication1 {

   
    public static void main(String[] args) throws IOException {
         
            Document doc = Jsoup.connect("http://jkpsc.nic.in/").get();
            Element ul = doc.getElementById("whatsNew");
            Elements li = ul.select("a");
            
            for (Element e : li) {
                
                String name = e.text();
                String url = e.absUrl("href");    
          
                
                if (name!=null || url!=null && ! name.equals("") || !name.equals("http://jkpsc.nic.in/")){
                    System.out.print("\n\nNAME: " + name + "\nURL: " + url); 
                }
            }
            
    }
    
}
```

## Demo

![Demo](https://raw.githubusercontent.com/xposed73/jsoup-crawler/main/src/demo.png)

