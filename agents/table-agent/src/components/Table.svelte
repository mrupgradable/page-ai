<script>
  export let data = []; // Array of table data objects
</script>

<div class="overflow-x-auto">
  <table class="min-w-full bg-white border border-gray-200 rounded-lg shadow-md">
    <thead class="bg-gray-100">
      <tr>
        <th class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider border-b">
          Instrument
        </th>
        <th class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider border-b">
          Market
        </th>
        <th class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider border-b">
          Quantity
        </th>
        <th class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider border-b">
          Instant
        </th>
      </tr>
    </thead>
    <tbody class="divide-y divide-gray-200">
      {#each data as row, i}
        <tr class={i % 2 === 0 ? 'bg-white' : 'bg-gray-50'}>
          <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-900">
            {row.instrument}
          </td>
          <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-900">
            {row.market}
          </td>
          <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-900">
            {row.quantity}
          </td>
          <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-900">
            {row.instant}
          </td>
        </tr>
      {:else}
        <tr>
          <td colspan="4" class="px-6 py-4 text-center text-sm text-gray-500">
            No data available
          </td>
        </tr>
      {/each}
    </tbody>
  </table>
</div>