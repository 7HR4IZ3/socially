<script>
    import "../app.css";
    import Header from "../components/Header.svelte";
    import Sidebar from "../components/Sidebar.svelte";
</script>

<div class="bg-muted/40 flex min-h-screen w-full flex-col">
    <Sidebar />
    <div class="flex flex-col sm:gap-4 sm:py-4 sm:pl-14">
        <Header />
       <slot></slot>
    </div>
</div>
