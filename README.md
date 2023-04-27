- 👋 Hi, I’m @Giovanixa
- 👀 I’m interested in ...
- 🌱 I’m currently learning ...
- 💞️ I’m looking to collaborate on ...
- 📫 How to reach me ...

<!---
Giovanixa/Giovanixa is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
public class Cola {
    Nodo colas[];
     private Nodo inicio, nuevo, p,q;
    public Cola(int n){
        colas=new Nodo[n];
        inicio =  null;
        nuevo = null;
    }
    public void insertarInicio(String nombre, int gravedad){
        nuevo = new Nodo(nombre, gravedad);
        if(inicio ==null){
            inicio=nuevo;
        } else {            
            nuevo.setSgte(inicio);
            inicio= nuevo;
        }
    }
    public void insertarFinal(String nombre, int gravedad){
        nuevo = new Nodo(nombre, gravedad);
         if(inicio ==null){
            inicio=nuevo;
        } else {              
             p=inicio;
             while(p.getSgte()!=null){
                 p= p.getSgte();
             }
            p.setSgte(nuevo);
        }
    }
    public String mostrar(){
        String mensaje=""   ;
        p=inicio;
        while(p!=null){
            mensaje += p.getNombre()+p.getGravedad()+"\n";
            p=p.getSgte();           
        }
        return mensaje;
    }
    public void EliminarAlinicio(){
        if(inicio!=null){
            inicio= inicio.getSgte();
        }else{
            System.out.println("No hay un elemento en la lista");
        }
    }
        public void EliminarAlFinal(){
        if(inicio!=null){
            if(inicio.getSgte()==null){
                inicio= null;
        }else{
            p=inicio;
            while(p.getSgte()!=null){
                q=p;
                p=p.getSgte();
            }
               q.setSgte(null);
        }
        }else{
            System.out.println("No hay un elemento en la lista");
        }
    }
}


