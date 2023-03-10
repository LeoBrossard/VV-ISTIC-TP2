# Code of your exercise


## In the visitor script
```
ArrayList<String> list = new ArrayList<>();
ArrayList<String> listOfMethod = new ArrayList<>();

@Override
public void visit(ClassOrInterfaceDeclaration declaration, Void arg) {
    visitTypeDeclaration(declaration, arg);
    for (FieldDeclaration field : declaration.getFields()) {
        for(int i = 0; i < field.getModifiers().size(); i++){
            if (field.getModifiers().get(i).getKeyword().asString().equals("private")){
                list.add(field.getVariable(i).getNameAsString());
            }
        } 
    }        
}
```
## In the Main script
```
for (String string : printer.list) {
    if(!printer.listOfMethod.contains("get"+string.toLowerCase())){
        System.out.println(string);
    }
}
```
I check with JavaParser for every Class if there is a private Variable and if any "get<variable-name>" function exist anywhere in the code.
