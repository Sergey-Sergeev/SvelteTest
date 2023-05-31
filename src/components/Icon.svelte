<script>
    export let name;
    const icons = [
        {
            name: 'check-mark',
            path: 'static/favicon.png',     
        },
        {
            name: 'delete',
            path: 'none'
        },
    ];

    let icon = icons.find((item) => item.name === name);
</script>

