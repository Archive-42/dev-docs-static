# PaymentAddress.regionCode

**Deprecated**

This feature is no longer recommended. Though some browsers might still support it, it may have already been removed from the relevant web standards, may be in the process of being dropped, or may only be kept for compatibility purposes. Avoid using it, and update existing code if possible; see the [compatibility table](#browser_compatibility) at the bottom of this page to guide your decision. Be aware that this feature may cease to work at any time.

The `regionCode` read-only attribute of the [`PaymentAddress`](../paymentaddress) interface returns a one-, two-, or three-alphanumeric code ([`DOMString`](../domstring)) representing the region of the address (e.g., "CA" for California, or "11" for Lisbon, Portugal).

The code is derived from the ISO 3166-2 standard, which defines codes for identifying the subdivisions (e.g., states, provinces, autonomous regions, etc.) of all countries in the world.

If the browser can't determine the region code, or the country doesn't use regions for postal addresses, it returns an empty string.

## Syntax

    var regionCode = paymentAddress.regionCode;

### Value

A [`DOMString`](../domstring) indicating the one to three character alphanumeric code representing the region portion of the address. This should correspond to `region`, but should be the ISO 3166--2 standard's region code. The string is empty if the region code couldn't be determined, isn't needed for the address's [`country`](country), or was not provided.

BCD tables only load in the browser

- [United Nations: UN/LOCODE Country Subdivisions ISO 3166-2](https://www.unece.org/cefact/locode/subdivisions.html)
- [ISO 3166-2](https://en.wikipedia.org/wiki/ISO_3166-2) on Wikipedia

<a href="https://developer.mozilla.org/en-US/docs/Web/API/PaymentAddress/regionCode" class="_attribution-link">https://developer.mozilla.org/en-US/docs/Web/API/PaymentAddress/regionCode</a>
