<!--
A repository template for creating new examples.
-->

# MaskedInput for Blazor - How to create an input with credit card number, month/year, CVV and ZIP

Here is an example of how to use MaskedInput component to show a large input with credit card number, month/year, CVV and ZIP as shown below:

![alt text](https://github.com/dlvaleroso98/How-to-create-MaskedInput-with-credit-card-number-valid-month-year-CVV-and-ZIP/blob/21.2.3%2B/sample.jpg)

The main idea is to use multiple MaskedInputs for Card number, valid month/year, CVV and ZIP. Then remove their borders and put them inside a div container.

# Razor

```razor
<div class="container-input" >
    <div>
        <DxMaskedInput @bind-Value="@CardNumber"
                       InputCssClass="border-none"
                       Mask="0000 0000 0000 0000"
                       NullText="Card Number">
        </DxMaskedInput>
    </div>
    <div>
        <DxMaskedInput @bind-Value="@Date"
                       Mask="@DateTimeMaskValue"
                       InputCssClass="border-none"
                       NullText="MM/YY"
                       CssClass="width-sm">
        </DxMaskedInput>
        <DxMaskedInput @bind-Value="@CVV"
                       InputCssClass="border-none"
                       Mask="000" 
                       CssClass="width-sm"
                       NullText="CVV">
        </DxMaskedInput>
        <DxMaskedInput @bind-Value="@ZIP"
                       InputCssClass="border-none"
                       Mask="00000" CssClass="width-sm"
                       NullText="ZIP">
        </DxMaskedInput>
    </div>
</div>

@code {
    DateTime? Date { get; set; } = null;
    string DateTimeMaskValue = "MM/yy";
    long? CardNumber { get; set; }
    int? CVV { get; set; }
    int? ZIP { get; set; }
}
```
# CSS

```css
    .border-none {
        border: 0 !important;
        box-shadow: none !important;
    }
    .container-input {
        display: flex;
        justify-content: space-between;
        width: 500px;
        border: 2px solid black ;
    }
        .container-input > div {
            display: flex;
        }
    .width-sm {
        width:75px;
    }
    .width-la {
        width: 250px;
    }
```

<!-- default file list -->

## Files to Look At

- [Index.razor](./CS/BlazorServerApp/Pages/Index.razor)

<!-- default file list end -->

<!--

## Documentation

- link
- link
- ...

## More Examples

- link
- link
- ...

-->
