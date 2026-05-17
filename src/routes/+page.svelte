<script lang="ts">
    import {
        mdiChevronDown,
        mdiContentCopy,
        mdiContentCut,
        mdiContentPaste,
    } from "@mdi/js";
    import {
        Button,
        Icon,
        Menu,
        MenuButton,
        MenuField,
        MenuItem,
        Stack,
        Toggle,
    } from "svelte-ux";

    const options = [
        { label: "Cut", value: "cut" },
        { label: "Copy", value: "copy" },
        { label: "Paste", value: "paste" },
    ];

    const optionsWithIcons = [
        { label: "Cut", value: "cut", icon: mdiContentCut },
        { label: "Copy", value: "copy", icon: mdiContentCopy },
        { label: "Paste", value: "paste", icon: mdiContentPaste },
    ];
</script>

<h1>Welcome to SvelteKit</h1>

<Stack horizontal gap="md">
    <MenuButton options={optionsWithIcons}>
        <svelte:fragment slot="selection" let:value>
            {#if value}
                <Icon data={value?.icon ?? mdiChevronDown} /> {value.label}
            {:else}
                No selection
            {/if}
        </svelte:fragment>
    </MenuButton>

    <MenuButton options={optionsWithIcons} menuIcon={null}>
        <svelte:fragment slot="selection" let:value>
            <Icon data={value?.icon ?? mdiChevronDown} />
        </svelte:fragment>
    </MenuButton>

    <MenuButton {options} variant="fill" color="primary" />

    <Toggle let:on={open} let:toggle let:toggleOff>
        <Button on:click={toggle}>
            Click me
            <Menu {open} on:close={toggleOff}>
                <MenuItem>Refresh</MenuItem>
                <MenuItem>Settings</MenuItem>
                <MenuItem>Help</MenuItem>
                <MenuItem>Sign In</MenuItem>
                <MenuItem disabled>Disabled</MenuItem>
            </Menu>
        </Button>
    </Toggle>

    <MenuField label="View" {options} />
</Stack>
