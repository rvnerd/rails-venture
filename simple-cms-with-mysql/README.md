###   rails new lynda-simples-cms-test-connection-with-mysql -d mysql

	   then just changed the name of the database to be equal to the one
	   that exists in my mysql database

---

###   rails server

---

###   rails generate controller demo index

---

### 3 ways of doing a route (the last two can be configured to match whatever you want)

	  get 'demo/index'

	  get 'demo/' => 'demo#index'

	  match "demo/",
	    :to => "demo#index",
	    :via => :get

---

### specifying a default route for every request
  match ":controller(/:action(/:id))", :via => :get

### the same as the above but we can specify the format (JSON for example)
#### this is not good practice
  match ":controller(/:action(/:id(.:format)))", :via => :get

---

controller/action/id/page/name
/demo/hello/1?page=3&name=rivalerio

id is special so it becames to the left of the question mark.

to access parameters that are passed via GET or POST we use the "params" keyword

params is what's called an hash with indiferent access, i.e,
we can access the parameter's values by referencing a string or a hash symbol

params['id']
params[:id]

---

para fazer um dump em rails de todas as tabelas existentes na BD,
como faço com o phalcon-models, executa-se o seguinte comando:

rake db:schema:dump    ou ainda, rake db:migrate segundo a documentação

nota: é também possível passar variáveis como argumento

		rake db:schema:dump RAILS_ENV=production

o default é development
---
	depois é necessário gerar uma migration para poder usufruir do ficheiro
	schema.rb que foi criado automaticamente

---

 para listar todos os comandos existentes para o comando "rake":

 	rake -T

retorna todas as "Tasks" existentes

---
		  | COLUMN TYPES |
	  	  |--------------|
	  	  | boolean      |
	  	  | date         |
	  	  | datetime     |
	  	  | decimal      |
	  	  | float        |
	  	  | inte         |
	  	  | string       |
	  	  | text         |
	  	  | time         |

		  |    COLUM OPTIONS     |
		  |----------------------|
		  | :limit => size       |
		  | :default => value    |
		  | :null => true/false  |
		  | :precision => number |
		  | :scale => number     |

---
	|    TABLE MIGRATION METHODS    |
	| ----------------------------- |
	| create_table(table, options)  |
	| drop_table(end)               |
	| rename_table(table, new_name) |

---

	|           COLUMN MIGRATION METHODS          |
	| ------------------------------------------- |
	| add_column(table, column, type, options)    |
	| remove_column(table, columun)               |
	| rename_column(table, column, new_name)      |
	| change_column(table, column, type, options) |
	| add_index(table, column)                    |


execute(sql)

---

## aplica as migations que ainda não foram executadas, isto é, que não constam na table schema_migrations na base de dados
rake db:migrate		#isto faz com que o método up seja chamado

## reverte todas as migrations para a versão passada, neste caso, reverte tudo:
rake db:migrate VERSION=0    #isto faz com que o método down seja chamado

---

rake db:migrate
rake db:migrate:status
rake db:migrate VERSION="TIME_STAMP_HERE" se eu quiser ir para alguma versão em particular
rake db:migrate

---
# generating a model

rails g model SingleNameAndUpperCase

por exemplo:

	rails g model Subject
	rails g model Page
	rails g model Section

---
---
---
---
---

############################################################################
sometimes rake db:migrate throws an error and it can be solved with:
	bundle exec rake db:migrate
############################################################################


