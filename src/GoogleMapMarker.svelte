<script>
  import { getContext } from 'svelte'
  import { key } from './contexts.js'

  const { getMap } = getContext(key)
  const map = getMap()

  export let lat
  export let lng
  export let icon

  // eslint-disable-next-line no-new
  const marker = new window.google.maps.Marker({
    position: { lat, lng },
    icon,
    map
  })

  export function removeMarker()
  {
    marker.setMap(null);
  }
</script>
