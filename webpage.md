In the following tutorial, replace `<new-page>` with the title of your page.

Create a new subdirectory for your page `mkdir src/pages/<new-page>` and create an idex file `touch src/pages/<new-page>/index` e.g.
```js
import type { FC } from 'react'

const NewPage: FC = ({
}) => {
  return (
    <>
        Hello, welcome to my new page! 
    </>
  )
}

export default NewPage

```
. You will now be able to navigate to this page by typing the url `http://localhost:3000/<new-page>` into your browser. To add your new page to the primary navigation bar, open `src/components/navigation/PrimaryNavBar.tsx` and add `<NavButton title="<Page Title>" link="/<new-page>" />` into the sequence of nav buttons, e.g.
```js
const PrimaryNavBar: FC = () => {
  return (
    <div className="px-4">
      <Navbar fluid={true} rounded={true}>
        <Link href="/home">
          <Image
            src={toriisLogo as HTMLImageElement}
            className="my-3 h-12 w-auto"
            alt="TORIIS Logo"
          />
        </Link>
        <Navbar.Toggle />
        <Navbar.Collapse>
          <NavButton title="Home" link="/home" />
          <NavButton title="Take Action" link="/take-action" />
          <NavButton title="Why Divest?" link="/fossil-fuel" />
          <NavButton title="Investment Database" link="/investments" />
          <NavButton title="New Page" link="/new-page" /> {/* Button for new page */}
          <div className="hidden w-fit flex-col justify-center md:flex">
            <AuthButton />
          </div>
        </Navbar.Collapse>
      </Navbar>
    </div>
  )
}
```
