1) Open app folder and click on page.tsx then remove everything from the return statement
2) Use div tag to get a structure
  ```


export default function Home() {
  return (
   <div>

    
    Hello World!
    </div>
  );
}

```

   <img width="1082" height="380" alt="image" src="https://github.com/user-attachments/assets/924bb323-a20e-47b2-9df4-1265d1122572" />

3) How to use className
   ```
   import Image from "next/image";

export default function Home() {
  return (
   <div className="text-4xl font-bold text-green-500">


    Hello World!
    </div>
  );
}   ```
<img width="1095" height="300" alt="image" src="https://github.com/user-attachments/assets/88f52c95-0871-4432-99ab-c0cbb7d51b56" />
4) install shadcn ui 
```
npx shadcn@latest --version
```
Output:
````
shadcn@3.6.2
````
Now innstall this version
```
npx shadcn@2.5.0 init
```
Make sure u use --legacy user
5) Add all the components
```
npx shadcn@2.5.0 add --all
```
6) Create new button to know about working
 ```
   import { Button } from "@/components/ui/button";
 import Image from "next/image";

export default function Home() {
  return (
 <Button>
  Hi
 </Button>
  );
}

   ```
<img width="645" height="221" alt="image" src="https://github.com/user-attachments/assets/321b1767-c5d3-46a9-a683-057eff51d162" />
7) Add this 
```
 custom:"text-white bg-purple-500 border-2 border-red-500 hover:bg-purple-600"
```
<img width="1088" height="582" alt="image" src="https://github.com/user-attachments/assets/ddf77540-fc0c-4f1e-8ef9-de746b3c0037" />
