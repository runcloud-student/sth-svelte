<script>
    import { Router, Route, Link } from "svelte-navigator";
    import BackButton from "./BackButton.svelte";
    import ForwardButton from "./ForwardButton.svelte";
    import Example1 from "./Example1.svelte";
    export let name;
</script>

<Router>
    <header>
        <h1>History</h1>

        <nav>
            <BackButton />
            <ForwardButton />
            <Link to="/">Base</Link>
            <Link to="home">Home</Link>
            <Link to="about">About</Link>
            <Link to="example1/{name}">Example1</Link>
        </nav>
    </header>

    <main>
        <Route path="example1/*example1Route" component={Example1} />

        <Route path="home">
            <h3>Home</h3>
            <p>Home sweet home...</p>
        </Route>

        <Route path="about">
            <h3>About</h3>
            <p>That's what it's all about!</p>
        </Route>

        <Route>
            <h3>Default</h3>
            <p>No Route could be matched.</p>
        </Route>
    </main>
</Router>
