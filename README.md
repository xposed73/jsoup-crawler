
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
    
}
```
