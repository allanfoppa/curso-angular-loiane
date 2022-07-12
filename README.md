# CURSO ANGULAR LOIANE

[Link do curso](https://www.youtube.com/watch?v=qJnjz8FIs6Q&list=PLGxZ4Rq3BOBpwaVgAPxTxhdX_TfSVlTcY&ab_channel=LoianeGroner)

## ANGULAR CLI

```shell
# verifica a versão.
ng version
```

## MODULES

```markdown
├── = Representa uma pasta no projeto

└── = Representa um arquivo

|├── app
|   ├── components
|     ├── table_module_name
|       ├── interface
|         └── interface_name.interface.ts
|       ├── settings
|         └── displayedColumns.settings.ts
|       └── table_module_name.css
|       └── table_module_name.html
|       └── table_module_name.spec.ts
|       └── table_module_name.module.ts
|     ├── form_module_name
|       ├── interface
|         └── interface_name.interface.ts
|       ├── settings
|         └── payload.settings.ts
|       └── form_module_name.css
|       └── form_module_name.html
|       └── form_module_name.spec.ts
|       └── form_module_name.module.ts
|       └── form_module_name.service.ts
|   ├── constants
|   ├── views
|   ├── services
|     ├── table_module_name
|       └── table_module_name.service.ts
|   ├── third-party
|   ├── pipes
```

## RXJS

```typescript
// GET:
list(): Observable<Array<Item>> {
  return this.httpCliente.get('endpoint', params)
  .pipe(
    first(), // Recebe apenas uma vez os dados da requisição
    delay(5000), // atraso manual da requisição para testes
    tap(list => console.log(list)), // Para debuggar
  )
}
```

## PIPE

```shell
# cria um pipe chamado square
ng generate pipe square

// Output
CREATE src/app/square.pipe.spec.ts (187 bytes)
CREATE src/app/square.pipe.ts (217 bytes)
UPDATE src/app/app.module.ts (2931 bytes)
```

```typescript
import { Pipe, PipeTransform } from '@angular/core';

@Pipe({
  name: 'square'
})
export class SquarePipe implements PipeTransform {

  transform(value: number): number {
    return value * value;
  }

}
```

```html
<!-- VALOR PASSADO | CUSTOM PIPE -->
<!-- 4 * 4 = 16 -->
<p>{{ 4 | square}}</p>
```

## ROUTING

```typescript

// constructor
constructor(
  private router: Router,
  private route: ActivatedRoute
)

// method
mehod(): void {
  this.router.navigate(
    commands: ['new'],
    extras: {
      relativeTo: this.route // é interessante passar por aqui sendo que quando a necessidade de alterar o path no módulo, não é necessário alterar em commands, por ser relativo a rota ativa.
    }
  )
}

```

## FORMS

### FORMBUILDER

[Exemplo de formulário em grupo](https://angular.io/guide/reactive-forms)
