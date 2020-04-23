# How to work with Accordion using C# in Xamarin.Forms (SfAccordion)

You can create [SfAccordion](https://help.syncfusion.com/xamarin/accordion/getting-started?) using the C# in Xamarin.Forms.

You can also refer the following article.

https://www.syncfusion.com/kb/11437/how-to-work-with-accordion-using-c-in-xamarin-forms-sfaccordion

**C#**

Creating the SfAccordion in the constructor of MainPage.
``` c#
namespace AccordionXamarin
{
    public partial class MainPage : ContentPage
    {
        SfAccordion Accordion; 
        public MainPage()
        {
            InitializeComponent();
            InitializeAccordionItems();
            Accordion.ExpandMode = ExpandMode.Multiple;
            this.Content = Accordion;
        }
        private void InitializeAccordionItems()
        {
            Accordion = new SfAccordion();
            Accordion.Items.Add(GenerateInvoiceHeaderAccordion());
            Accordion.Items.Add(GenerateInvoiceItemsAccordion());
            Accordion.Items.Add(GeneratePaymentDetailsAccordion());
        }
 
        private AccordionItem GenerateInvoiceHeaderAccordion()
        {
            var item = new AccordionItem();
            var headerGrid = new Grid() { Padding = new Thickness(10, 0, 0, 10) };
            var headerLabel = new Label() { Text = "Invoice Date", HeightRequest = 50, VerticalTextAlignment = TextAlignment.Center };
            headerGrid.Children.Add(headerLabel);
 
            var contentGrid = new Grid() { Padding = new Thickness(10, 0, 0, 10), BackgroundColor = Color.NavajoWhite };
            var contentLabel = new Label() { Text = "11.03 AM, 15 January 2019", HeightRequest = 50, VerticalTextAlignment = TextAlignment.Center };
            contentGrid.Children.Add(contentLabel);
 
            item.Header = headerGrid;
            item.Content = contentGrid;
            return item;
        }
 
        private AccordionItem GenerateInvoiceItemsAccordion()
        {
            var item = new AccordionItem();
            var headerGrid = new Grid() { Padding = new Thickness(10, 0, 10, 10) };
            var headerLabel = new Label() { Text = "Item (s)", HeightRequest = 50, VerticalTextAlignment = TextAlignment.Center };
            headerGrid.Children.Add(headerLabel);
 
            var contentGrid = new Grid() { Padding = new Thickness(10, 0, 10, 10), BackgroundColor = Color.NavajoWhite };
            contentGrid.RowDefinitions.Add(new RowDefinition() { Height = new GridLength(1, GridUnitType.Auto) });
            contentGrid.RowDefinitions.Add(new RowDefinition() { Height = new GridLength(1, GridUnitType.Auto) });
            contentGrid.RowDefinitions.Add(new RowDefinition() { Height = new GridLength(1, GridUnitType.Auto) });
            contentGrid.RowDefinitions.Add(new RowDefinition() { Height = new GridLength(1, GridUnitType.Auto) });
            contentGrid.RowDefinitions.Add(new RowDefinition() { Height = new GridLength(1, GridUnitType.Auto) });
 
            contentGrid.ColumnDefinitions.Add(new ColumnDefinition() { Width = new GridLength(1, GridUnitType.Star) });
            contentGrid.ColumnDefinitions.Add(new ColumnDefinition() { Width = new GridLength(1, GridUnitType.Star) });
 
            var contentLabel0 = new Label() { Text = "2018 Subaru Outback" };
            var contentLabel2 = new Label() { Text = "Door Edge Guard Kit" };
            var contentLabel1 = new Label() { Text = "All-Weather Mats" };
            var contentLabel3 = new Label() { Text = "Rear Bumper Cover" };
            var contentLabel4 = new Label() { Text = "Total Amount Paid", FontAttributes = FontAttributes.Bold };
            var contentLabel5 = new Label() { Text = "$35,700.00", HorizontalTextAlignment = TextAlignment.End };
            var contentLabel6 = new Label() { Text = "$105.00", HorizontalTextAlignment = TextAlignment.End };
            var contentLabel7 = new Label() { Text = "$100.00", HorizontalTextAlignment = TextAlignment.End };
            var contentLabel8 = new Label() { Text = "$95.00", HorizontalTextAlignment = TextAlignment.End };
            var contentLabel9 = new Label() { Text = "$36,000.00", HorizontalTextAlignment = TextAlignment.End, FontAttributes = FontAttributes.Bold };
 
            contentGrid.Children.Add(contentLabel0, 0, 0);
            contentGrid.Children.Add(contentLabel1, 0, 1);
            contentGrid.Children.Add(contentLabel2, 0, 2);
            contentGrid.Children.Add(contentLabel3, 0, 3);
            contentGrid.Children.Add(contentLabel4, 0, 4);
            contentGrid.Children.Add(contentLabel5, 1, 0);
            contentGrid.Children.Add(contentLabel6, 1, 1);
            contentGrid.Children.Add(contentLabel7, 1, 2);
            contentGrid.Children.Add(contentLabel8, 1, 3);
            contentGrid.Children.Add(contentLabel9, 1, 4);
 
            item.Header = headerGrid;
            item.Content = contentGrid;
            return item;
        }
 
        private AccordionItem GeneratePaymentDetailsAccordion()
        {
            var item = new AccordionItem();
            var headerGrid = new Grid() { Padding = new Thickness(10, 0, 10, 10) };
            var headerLabel = new Label() { Text = "Payment Details", HeightRequest = 50, VerticalTextAlignment = TextAlignment.Center };
            headerGrid.Children.Add(headerLabel);
 
            var contentGrid = new Grid() { Padding = new Thickness(10, 0, 10, 10), BackgroundColor = Color.NavajoWhite };
            contentGrid.RowDefinitions.Add(new RowDefinition() { Height = new GridLength(1, GridUnitType.Auto) });
            contentGrid.RowDefinitions.Add(new RowDefinition() { Height = new GridLength(1, GridUnitType.Auto) });
            contentGrid.RowDefinitions.Add(new RowDefinition() { Height = new GridLength(1, GridUnitType.Auto) });
 
            contentGrid.ColumnDefinitions.Add(new ColumnDefinition() { Width = new GridLength(1, GridUnitType.Star) });
            contentGrid.ColumnDefinitions.Add(new ColumnDefinition() { Width = new GridLength(1, GridUnitType.Star) });
 
            var contentLabel0 = new Label() { Text = "Card Payment" };
            var contentLabel1 = new Label() { Text = "Third-Party coupons" };
            var contentLabel2 = new Label() { Text = "Total Amount Paid", FontAttributes = FontAttributes.Bold };
            var contentLabel3 = new Label() { Text = "$31,000.00", HorizontalTextAlignment = TextAlignment.End };
            var contentLabel4 = new Label() { Text = "$5,000.00", HorizontalTextAlignment = TextAlignment.End };
            var contentLabel5 = new Label() { Text = "$36,000.00", HorizontalTextAlignment = TextAlignment.End, FontAttributes = FontAttributes.Bold };
 
            contentGrid.Children.Add(contentLabel0, 0, 0);
            contentGrid.Children.Add(contentLabel1, 0, 1);
            contentGrid.Children.Add(contentLabel2, 0, 2);
            contentGrid.Children.Add(contentLabel3, 1, 0);
            contentGrid.Children.Add(contentLabel4, 1, 1);
            contentGrid.Children.Add(contentLabel5, 1, 2);
 
            item.Header = headerGrid;
            item.Content = contentGrid;
            return item;
        }
    }
}
```
**Output**

![AccordionC#](https://github.com/SyncfusionExamples/accordion-in-code-xamarin/blob/master/ScreenShots/AccordionProgrammatic.png)
