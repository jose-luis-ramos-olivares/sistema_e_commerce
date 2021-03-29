# README

Implementacion de la lista de productos del catalogo:
 - En primer lugar, la vista home para que logre mostrar solamente productos unicos (los cuales estan en la tabla base_product) 
 - en segundo lugar la vista home debe mostrar solamente productos unicos que tengan stock en alguna de sus variaciones
 - las variaciones se encuentran en la tabla product la cual es hija es base_product

para poder plasmar esto en la vista debemos crear 2 metodos:
 - el primero se encarga de retornar todos los productos hijos de base_product
    def children
       children = self.products
    end
 - el segundo se encarga de retornar el stock total de los productos hijos de base_product
    def children_stock
        self.products.sum(:stock)
    end

`
Baseproducts.all.each do |baseproduct|
    baseproduct.children
end
