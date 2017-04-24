API methods that return a collection of results are always paginated. Paginated results will include a Link (see [RFC-5988](https://tools.ietf.org/html/rfc5988)) response header with the following information.

* next. The corresponding URL is the link to the next page.
* prev. The corresponding URL is the link to the previous page.
* last. The corresponding URL is the link to the last page.
* Note that when this header is not set, there is only one page, the first page, of results.

As of February 2017, we are transitioning to a new method for paging while maintaining backwards compatibility. Currently, the new method only supports providing a next link and is used by the following endpoints:

* GET: List EEOC
* GET: List User Roles

### Example Paging Header

    Link: <https://harvest.greenhouse.io/v1/candidates?page=2&per_page=2>; rel="next",
    <https://harvest.greenhouse.io/v1/candidates?page=474&per_page=2>; rel="last"

> Since paging mechanisms may differ per paginated endpoint and may change in the future, it is important to use the Link headers and not page manually by changing the paging-related query parameters.
