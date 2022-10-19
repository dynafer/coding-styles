# Typescript Coding Style
## I. Common Style
> ### 1. Use Camel Case for ...
> * local variables
> * local functions
> * arguments
> * private member variables and methods
> 
> ```Typescript
> let localVariable: object;   
> 
> class ClassName {
> 	private mVariable: object;
> 
> 	private getValue(someArgument: string) {
> 		...
> 	}
> }
> ```
> ### 2. Use Pascal Case for ...
> * exported variables
> * exported functions
> * public member variables and methods
> * classes
> * types
> * enums
> * interfaces
> * namespaces
> 
> ```Typescript
> export const SomeVariable: string = 'Some Strings...';
> export function SomeFunction(): void {
> 	return;
> }
> 
> type TSomeType = string[];
> 
> enum EColour {
> 	red,
> 	yellow,
> 	...
> }
> 
> interface ISomeInterface {
> 	...
> }
> 
> class ClassName {
> 	public Variable: string;
> 
> 	public SetValue(...) {
> 		...
> 	}
> }
> 
> namespace NSSome {
> 	...
> }
> ```
> 
> ### 3. Make everything understandable when naming it
> ```Typescript
> // Good Case
> const countryList: string[] = [...];
> let countryIndex: number = 0;
> export function GetCurrentCountry(): string {
> 	return countryList[countryIndex];
> }
> 
> // Bad Case
> const list: string[] = [...];
> let i: number = 0;
> export function GetCur(): string {
> 	return list[i];
> }
> ```
> 
> ### 4. Use verb + object for __*functions*__ and __*methods*__
> ```Typescript
> const countryList: string[] = [...];
> export function GetCountry(index: number): string {
> 	return countryList[index];
> }
> export function AddCountry(name: string): void {
> 	countryList.push(name);
> }
> ```
> 
> ### 5. Use verb such as __*Is, Should, Can, Has*__ or __*Third Person Verb*__ for functions > or methods that return __*boolean*__
> ```Typescript
> export function IsChangeable(): boolean {
> 	...
> }
> export function ShouldClean(): boolean {
> 	...
> }
> export function CanFix(): boolean {
> 	...
> }
> export function HasChildren(): boolean {
> 	...
> }
> export function Contains(): boolean {
> 	...
> }
> ```
> 
> ### 6. Start with ...
> * __*f*__ for float
> * __*b*__ for boolean
> * __*m*__ for private member variables
> * __*T*__ for types
> * __*E*__ for enums
> * __*I*__ for interfaces
> * __*NS*__ for namespaces
> ```Typescript
> let fPie: number = 3.14;
> let bChanged: boolean = false;
> class SomeClass {
> 	private mVariable: string = 'Some Strings...';
> }
> type TSomeType = string[] | string;
> enum ESomeEnums {
> 	...
> }
> interface ISomeInterface {
> 	...
> }
> namespace NSSomeName {
> 	...
> }
> ```
> 
> ### 7. Use all capital letters and underline for __*global constants*__ declared as ...
> * string
> * number
> * boolean
> ```Typescript
> declare global {
> 	interface Window {
> 		SOME_MAGIC_STRING: stirng,
> 		SOME_MAGIC_NUMBER: number,
> 		SOME_MAGIC_BOOLEAN: boolean,
> 	}
> 
> 	const SOME_MAGIC_STRING: string;
> 	const SOME_MAGIC_NUMBER: number;
> 	const SOME_MAGIC_BOOLEAN: boolean;
> }
> 
> export const SOME_MAGIC_STRING: string = 'Some Strings...';
> export const SOME_MAGIC_NUMBER: number = 421;
> export const SOME_MAGIC_BOOLEAN: boolean = true;
> ```
> 
> ### 8. Use __*const*__ for __*array*__ and __*object*__, except in exceptional cases
> ```Typescript
> const someArray: string[] = [];
> const someObject: object = [];
> ```
> 
> ### 9. Use __*template literals*__ for __*string*__ when referencing variables
> ```Typescript
> let fruitName: string = 'melon';
> 
> // Good Case
> let message: string = `The ${fruitName} is sweet!`;
> 
> // Bad Case
> let badMessage: string = 'The ' + fruitName + ' is sweet!';
> ```
> 
> ### 10. Order in ...
> * general and namespaces
> 	1. import
> 	2. declare
> 	3. global constants
> 	4. local constants
> 	5. local variables
> 	6. enums
> 	7. types
> 	8. interfaces
>	  9. local constances, variables using declared types, or interfaces
> 	10. functions
> 	11. namespaces
> 	12. classes
> * interfaces
> 	1. variables
> 	2. methods
> * classes
> 	1. public variables
> 	2. protected variables
> 	3. private variables
> 	4. methods
> 
> ### 11. Use __*for const ... of ...*__ if index isn't required
> * Allow only __*reduce*__ and __*reduce*__ built-in methods
> ```Typescript
> const someArray: string[] = [..., ..., ...];
> const someObject: object = { ... };
> 
> for (const item of someArray) {
> 	...
> }
> 
> const addedString: string = someArray.reduce((prev, current, index, array) => {
> 	return `${prev}[${current}]`;
> });
> 
> const filteredString: string[] = someArray.reduce((item, index) => {
>   return someArray.indexOf(item) === index;
> });
> 
> for (const [key, value] of Object.entries(someObject)) {
> 	...
> }
> 
> for (let index = 0; index < someArray.length; ++ index) {
> 	if (index === 1) break;
> 	...
> }
> ```
