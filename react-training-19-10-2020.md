# React Training - 19.10.2020 Botega

## Remember
- Sterowanie logiką z jednego miejsca
- Smart/Dump komponenty - nie w przypadku uzycia hooków - bo traci to sens
- Wymuszenie re-render - uzyj dump `setState`
- ReRenderowanie  - gdy zmienia się props,stan,context. Jeśli rodzic się przerednerowywuje to dzieci tez (prosta optymalizacja z `useMemo`)
- Tylko `REF` idzie do góry, kady inny przypadek to `one data flow`
- Kontekst co do idei nie powinien zwracać setterów i getterów ale API wyzszego rzędu (np pobierac nowe dane po zmianie filtrów)
- Podniesienie aplikacji React na bazie CRA, to tylko kopia `package.json` z nowej wersji
- Instalować typy dla paczek npm (jeśli nie wbudowane) `@types/package_name`
- Konteksty - łaczycz podobne dane zamiast mnozyc konteksty np. Kraj,Waluta
- Provider - musi mieć `children` jak i `value` // Value jest uywane przez `useContext`
- Mozna sobie kilka providerow do jednego kontekstu stworzyc i w zaleznosci od sytuacji zwracać odpowiedniego (Michał Skorupa)
- Przy zmianie providera, tylko konsumeci kontekstu są przeładowywani
- Do kontekstu bez obaw ładować metody (patrz wyzej) np funkjce obliczające zarobki
- Typy Implicite vs Explicite :  `type A = ReturnType<methodName>` albo `type A = ReturnType<typeof methodName>`  VS ręczne wypisywanie
- Zamiast contextow uzywac hookow z contextu (ukrywać semafory)
- Css properties w react `npm csstype`
- `*.d.ts` to same nagłó∑ki, zero implementacji ~~ Interface
- styled components - force output tag `<Blur as="div">`

- `e=textarea.current!` - `!` operator 
- Ref jest ustawioany zwrotnie po fazie commit. Efekty są po fazie Render
- `useEffect` -> po fazie Commit,  `useLayoutEffect` -> przed fazą commit

### Wydajność
- kompozycja wydajnośći - w funkcjach `map` nie inlinować komponentów bezpośrednio ale wstawić wyrenderowany wcześniej komponent przypisany do zmiennej
- single source of truth  - przekazywać całe obiekty (referencja) a nie wydzielone pola. Uzywać aliasów typów
- uzywac `useCallback` i `useMemo`  zwłaszcza w hookach 
- uzyć [https://github.com/pahen/madge] do sprawdzania drzewa - pomaga w cyklicznych zalenościach i rysowaniu grafu aplikacji
- destrtukturyazacja `let  {current} = useRef(..)` nie ma sensu, bo tworzona jest lokalna kopia prymitywu




## Implement
- aliasy typów ex: `type Zip = GQLBusiness['addresses']['visit'][0]['zip']`
- use `never` types
- introduce separated `*.d.ts` files
- Barel Index
- `readonly` types if neccessary 
- `useDebugValue` w custom hooku 
- more tools with `husky`  (but on push commit)
- dodatki do storybooka np. a11y (sotrybook-addon-*)
- w Messages - zapisywać do stora tmp wiadomości na unmount `useEffect` 

## TODO

- Play with Firebase
- Renew info about [BackstopJS](https://garris.github.io/BackstopJS/)
- Implementacja wzorca Repository
- Read more about `Memo`
- Rember about [CRA Rewired](https://www.npmjs.com/package/react-app-rewired) - dekorator na config Webpack
- Read more and renew info about lazyLoading React Components
- Read more about browserlist config i uzycia ES5/ES6  (w kontekscie IE11) (https://github.com/browserslist/browserslist)
- `ls .git/config` <- git hooki 
- SWR - stay while revalidate - doczytać
- EmployeesCost = check nested destruction
- Doczytać definicję side-effect
- sprawdzić BenefitDataContext i operator `!` (potwierdza ze coś istnieje, likwiduje undefined dla TS)
- css modules i CRA (by default) - check repo from training
- check function`blablala` - template literals function
- npm classnames/ @types/classnames 
- [Simple MDE](https://simplemde.com/)
- forwardedRef


----
- [CSS Types](https://www.npmjs.com/package/csstype)
- [React window](https://github.com/bvaughn/react-window)

