12/01/2023 22:41

Status: #information 

Tags: [[Bizagi]] [[JScript]]

In a JScript expression in Bizagi, we can filter an XPath using like this:

```jscript
<XPath[filter condition]>
```

Suppose we have a collection `Books` in my process `BuyBook`. In this process we have an boolean attribute to track books in the sale, `IsInSale`. If I want to filter books in the sale, I can do it like this:

```jscript
<BuyBook.Books[IsInSail=true]
```

---
# References

https://help.bizagi.com/bpm-suite/en/index.html?filtering_xpath.htm