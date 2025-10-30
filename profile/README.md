<p align="center">
    <a href="https://github.com/php-testo/testo"><img alt="TESTO"
         src="https://github.com/php-testo/.github/blob/1.x/resources/logo-full.svg?raw=true"
         style="width: 3in; display: block"
    /></a>
</p>

<br />

**Testo** (pronounced [test-oh], meaning "dough" in East and South Slavic languages) — is an extensible testing framework for PHP.
Built for scenarios requiring complete customization of the testing process: SDKs, framework tools, complex integrations.

Unlike other testing frameworks, Testo provides all at once: familiar and convenient PHP syntax,
unprecedented extensibility and customizability,
and a simple yet powerful architecture based on a minimal core and middleware system.

```php
#[Test(description: 'Start Temporal workflow via API and ensure no memory leaks occur during the process')]
#[RetryPolicy(maxAttempts: 2, markFlaky: false)]
function acceptanceTest(
    RouterInterface $router,
): void {
    $request = new Request('POST', '/api/start-workflow');

    $response = $router->process($request);

    # Assert that there are no memory leaks
    Assert::leaks(request: $request, response: $response);
    Assert::same(200, $response->getStatusCode());
}
```

Like dough, you can mold and shape it into any testing infrastructure you need.

We believe developers should have full control over their testing environment, and Testo delivers exactly that.
