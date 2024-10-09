- basic kaam kro tailwind vale -1 add to body tailwind script

# ADD Tailwind using Post CSS

> > Steps

- npm init -y // pakage.json file ajayegi ans isme hm baadme local server bnayenge
- Chose kro Uisng PostCSS from getting started se
- copy kro 1st code ki 1st line from tailwind css aur isime last me vite bhi daldo and paste in the terminal
  [npm install -D tailwindcss postcss autoprefixer] code from tailwind
  vite added at last [npm install -D tailwindcss postcss autoprefixer vite]
- Download vite => ye hme local server lake dega
- ab dusri line se iske krdo initialize
  [npx tailwindcss init] code of 1st code 2nd line
- ab path provide kro >> tailwind.config.js me jao aur josi file chlani hai unsabke path dedo >> chose \* for all files
- Add utility components >> style.css file bnao usko html se link kro and usme jake paste krdo
- Add the 3 statements to style.css file
- goto package.jason ->search script->inside it in test-> write "vite" -. to run vite server when test script run
- goto terminal and vhanpm run test krdo-> ye vite server chla dega

## Tailwind ki classes

- Tailwind ki site pe jao
- quick search pe jao
- css vali prop liko
- tailwind bta dega uska tailwind class kya hai

## eg

- background-color : bg-indigo-`950` ye no jitna zada hoga colour utna ghera hoga

  - Ye is colour ki max range hai jo website se liya hai ise zada dark nhi ho payega par ise light hosta hai "kaise pta try krke dekho"

- display:flex => `flex`
- justify-content:space-between => justify-between
- gap: 0px; => `gap-0` 0 gap between items
- text-color:white => `text-white`
- H tags yha apne aap height le saath nhi aate alag se dena pdta hai: text-5xl or 6xl or 7xl
- min-height:100px=>`min-h-[100px]`
- rounded border on large devide=> `rounded-lg`
