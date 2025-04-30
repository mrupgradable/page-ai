<script>
  import Table from './components/Table.svelte';
  
  // Sample data for the table
  const tableData = [
    {
      instrument: 'AAPL',
      market: 'NASDAQ',
      quantity: 100,
      instant: '2025-04-30T12:00:00Z'
    },
    {
      instrument: 'MSFT',
      market: 'NASDAQ',
      quantity: 50,
      instant: '2025-04-30T12:01:30Z'
    },
    {
      instrument: 'AMZN',
      market: 'NASDAQ',
      quantity: 25,
      instant: '2025-04-30T12:02:15Z'
    },
    {
      instrument: 'GOOGL',
      market: 'NASDAQ',
      quantity: 30,
      instant: '2025-04-30T12:03:45Z'
    }
  ];
</script>

<main class="container mx-auto p-4">
  <h1 class="text-2xl font-bold mb-4">Market Data Table</h1>
  <Table data={tableData} />
</main>

<style>
  :global(html, body) {
    margin: 0;
    padding: 0;
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen,
      Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
  }
</style>