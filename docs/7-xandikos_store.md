# Xandikos Store

[_Documentation generated by Documatic_](https://www.documatic.com)

<!---Documatic-section-Codebase Structure-start--->
## Codebase Structure

<!---Documatic-block-system_architecture-start--->
```mermaid
None
```
<!---Documatic-block-system_architecture-end--->

# #
<!---Documatic-section-Codebase Structure-end--->

<!---Documatic-section-xandikos.store.__init__.open_by_content_type-start--->
## [xandikos.store.__init__.open_by_content_type](7-xandikos_store.md#xandikos.store.__init__.open_by_content_type)

<!---Documatic-section-open_by_content_type-start--->
<!---Documatic-block-xandikos.store.__init__.open_by_content_type-start--->
<details>
	<summary><code>xandikos.store.__init__.open_by_content_type</code> code snippet</summary>

```python
def open_by_content_type(content: Iterable[bytes], content_type: str, extra_file_handlers) -> File:
    return extra_file_handlers.get(content_type.split(';')[0], File)(content, content_type)
```
</details>
<!---Documatic-block-xandikos.store.__init__.open_by_content_type-end--->
<!---Documatic-section-open_by_content_type-end--->

# #
<!---Documatic-section-xandikos.store.__init__.open_by_content_type-end--->

<!---Documatic-section-xandikos.store.__init__.open_by_extension-start--->
## [xandikos.store.__init__.open_by_extension](7-xandikos_store.md#xandikos.store.__init__.open_by_extension)

<!---Documatic-section-open_by_extension-start--->
```mermaid
flowchart LR
xandikos.store.__init__.open_by_extension-->xandikos.store.__init__.open_by_content_type
```

### Object Calls

* [xandikos.store.__init__.open_by_content_type](7-xandikos_store.md#xandikos.store.__init__.open_by_content_type)

<!---Documatic-block-xandikos.store.__init__.open_by_extension-start--->
<details>
	<summary><code>xandikos.store.__init__.open_by_extension</code> code snippet</summary>

```python
def open_by_extension(content: Iterable[bytes], name: str, extra_file_handlers: Dict[str, Type[File]]) -> File:
    (mime_type, _) = MIMETYPES.guess_type(name)
    if mime_type is None:
        mime_type = DEFAULT_MIME_TYPE
    return open_by_content_type(content, mime_type, extra_file_handlers=extra_file_handlers)
```
</details>
<!---Documatic-block-xandikos.store.__init__.open_by_extension-end--->
<!---Documatic-section-open_by_extension-end--->

# #
<!---Documatic-section-xandikos.store.__init__.open_by_extension-end--->

[_Documentation generated by Documatic_](https://www.documatic.com)