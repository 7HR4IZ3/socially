<script lang="ts">
    import House from "lucide-svelte/icons/house";
    import ChartLine from "lucide-svelte/icons/chart-line";
    import Package from "lucide-svelte/icons/package";
    import Package2 from "lucide-svelte/icons/package-2";
    import PanelLeft from "lucide-svelte/icons/panel-left";
    import Search from "lucide-svelte/icons/search";
    import ShoppingCart from "lucide-svelte/icons/shopping-cart";
    import UsersRound from "lucide-svelte/icons/users-round";

    import * as Breadcrumb from "$lib/components/ui/breadcrumb/index.js";
    import { Button } from "$lib/components/ui/button/index.js";
    import * as DropdownMenu from "$lib/components/ui/dropdown-menu/index.js";
    import { Input } from "$lib/components/ui/input/index.js";
    import * as Sheet from "$lib/components/ui/sheet/index.js";
</script>

<header
    class="bg-background sticky top-0 z-30 flex h-14 items-center gap-4 border-b px-4 sm:static sm:h-auto sm:border-0 sm:bg-transparent sm:px-6"
>
    <Sheet.Root>
        <Sheet.Trigger asChild let:builder>
            <Button
                builders={[builder]}
                size="icon"
                variant="outline"
                class="sm:hidden"
            >
                <PanelLeft class="h-5 w-5" />
                <span class="sr-only">Toggle Menu</span>
            </Button>
        </Sheet.Trigger>
        <Sheet.Content side="left" class="sm:max-w-xs">
            <nav class="grid gap-6 text-lg font-medium">
                <a
                    href="##"
                    class="bg-primary text-primary-foreground group flex h-10 w-10 shrink-0 items-center justify-center gap-2 rounded-full text-lg font-semibold md:text-base"
                >
                    <Package2
                        class="h-5 w-5 transition-all group-hover:scale-110"
                    />
                    <span class="sr-only">Acme Inc</span>
                </a>
                <a
                    href="##"
                    class="text-muted-foreground hover:text-foreground flex items-center gap-4 px-2.5"
                >
                    <House class="h-5 w-5" />
                    Dashboard
                </a>
                <a
                    href="##"
                    class="text-muted-foreground hover:text-foreground flex items-center gap-4 px-2.5"
                >
                    <ShoppingCart class="h-5 w-5" />
                    Orders
                </a>
                <a
                    href="##"
                    class="text-foreground flex items-center gap-4 px-2.5"
                >
                    <Package class="h-5 w-5" />
                    Products
                </a>
                <a
                    href="##"
                    class="text-muted-foreground hover:text-foreground flex items-center gap-4 px-2.5"
                >
                    <UsersRound class="h-5 w-5" />
                    Customers
                </a>
                <a
                    href="##"
                    class="text-muted-foreground hover:text-foreground flex items-center gap-4 px-2.5"
                >
                    <ChartLine class="h-5 w-5" />
                    Settings
                </a>
            </nav>
        </Sheet.Content>
    </Sheet.Root>
    <Breadcrumb.Root class="hidden md:flex">
        <Breadcrumb.List>
            <Breadcrumb.Item>
                <Breadcrumb.Link href="##">Dashboard</Breadcrumb.Link>
            </Breadcrumb.Item>
            <Breadcrumb.Separator />
            <Breadcrumb.Item>
                <Breadcrumb.Link href="##">Products</Breadcrumb.Link>
            </Breadcrumb.Item>
            <Breadcrumb.Separator />
            <Breadcrumb.Item>
                <Breadcrumb.Page>All Products</Breadcrumb.Page>
            </Breadcrumb.Item>
        </Breadcrumb.List>
    </Breadcrumb.Root>
    <div class="relative ml-auto flex-1 md:grow-0">
        <Search
            class="text-muted-foreground absolute left-2.5 top-2.5 h-4 w-4"
        />
        <Input
            type="search"
            placeholder="Search..."
            class="bg-background w-full rounded-lg pl-8 md:w-[200px] lg:w-[320px]"
        />
    </div>
    <DropdownMenu.Root>
        <DropdownMenu.Trigger asChild let:builder>
            <Button
                builders={[builder]}
                variant="outline"
                size="icon"
                class="overflow-hidden rounded-full"
            >
                <img
                    src="/images/placeholder-user.jpg"
                    width={36}
                    height={36}
                    alt="Avatar"
                    class="overflow-hidden rounded-full"
                />
            </Button>
        </DropdownMenu.Trigger>
        <DropdownMenu.Content align="end">
            <DropdownMenu.Label>My Account</DropdownMenu.Label>
            <DropdownMenu.Separator />
            <DropdownMenu.Item>Settings</DropdownMenu.Item>
            <DropdownMenu.Item>Support</DropdownMenu.Item>
            <DropdownMenu.Separator />
            <DropdownMenu.Item>Logout</DropdownMenu.Item>
        </DropdownMenu.Content>
    </DropdownMenu.Root>
</header>
