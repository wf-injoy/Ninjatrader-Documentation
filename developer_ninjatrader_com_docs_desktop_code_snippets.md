## [Code Snippets](https://developer.ninjatrader.com/docs/desktop/code_snippets\#code-snippets)

Code Snippets can provide you with useful code templates to speed up your coding process.

## [Understanding Code Snippet shortcuts](https://developer.ninjatrader.com/docs/desktop/code_snippets\#understanding-code-snippet-shortcuts)

| Shortcut | Method Signature |
| --- | --- |
| **dap** | `Draw.AndrewsPitchfork(this, "MyAndrewsPitchfork", false, 10, Close[10], 5, High[5], 0, Low[5], Brushes.Blue, DashStyleHelper.Solid, 1);` |
| **da** | `Draw.Arc(this, "MyDrawArc", false, 10, Close[10], 0, Close[0], Brushes.LimeGreen, DashStyleHelper.Dot, 2);` |
| **dd** | `Draw.ArrowDown(this, "MyArrowDown", false, 0, High[0], Brushes.Red);` |
| **du** | `Draw.ArrowUp(this, "MyArrowUp", false, 0, Low[0], Brushes.Red);` |
| **ddi** | `Draw.Diamond(this, "MyDiamond", false, 0, High[0] + 2 * TickSize, Brushes.Blue);` |
| **dt** | `Draw.Dot(this, "MyDot", false, 0, High[0] + 2 * TickSize, Brushes.Blue);` |
| **de** | `Draw.Ellipse(this, "MyEllipse", 10, Low[10], 0, High[0], Brushes.Blue);` |
| **di** | `Draw.ExtendedLine(this, "MyExtendedLine", 10, Close[10], 0, Close[0], Brushes.Blue);` |
| **dfc** | `Draw.FibonacciCircle(this, "MyFibonacciCircle", true, 10, Close[10], 0, Close[0]);` |
| **dfe** | `Draw.FibonacciExtensions(this, "MyFibonacciExtensions", true, 15, Close[15], 10, Close[10], 5, Close[5]);` |
| **dfr** | `Draw.FibonacciRetracements(this, "MyFibonacciRetracements", false, 10, Close[10], 0, Close[0]);` |
| **dft** | `Draw.FibonacciTimeExtensions(this, "MyFibonacciTimeExtensions", false, 10, Close[10], 0, Close[0]);` |
| **dg** | `Draw.GannFan(this, "MyGannFan", true, 10, Close[10]);` |
| **dh** | `Draw.HorizontalLine(this, "MyHorizontalLine", Close[0], Brushes.Blue);` |
| **dl** | `Draw.Line(this, "MyLine", 10, Close[10], 0, Close[0], Brushes.Blue);` |
| **dy** | `Draw.Ray(this, "MyRay", 10, Close[10], 0, Close[0], Brushes.Blue);` |
| **dr** | `Draw.Rectangle(this, "MyRectangle", 10, Low[10], 0, High[0], Brushes.Blue);` |
| **dre** | `Draw.Region(this, CurrentBar, 0, Bollinger(2, 14).Upper, Bollinger(2, 14).Lower, Brushes.Green, Brushes.Blue, 50);` |
| **drx** | `Draw.RegionHighlightX(this, "MyRegionHighlightX", 10, 0, Brushes.Blue);` |
| **dry** | `Draw.RegionHighlightY(this, "MyRegionHighlightY", High[0], Low[0], Brushes.Blue, Brushes.Green, 20);` |
| **drr** | `Draw.RiskReward(this, "MyRiskReward", false, 0, High[0], 10, Low[0], 2, true);` |
| **dru** | `Draw.Ruler(this, "tag1", true, 4, Low[4], 3, High[3], 1, Low[1]);` |
| **ds** | `Draw.Square(this, "MySquare", false, 0, High[0] + 2 * TickSize, Brushes.Blue);` |
| **dx** | `Draw.Text(this, "MyText", "Sample text ", 0, High[0] + 2 * TickSize, Brushes.Blue);` |
| **dxf** | `Draw.TextFixed(this, "MyTextFixed", "Text to draw", TextPosition.TopRight);` |
| **dtc** | `Draw.TrendChannel(this, "TrendChannel", true, 10, Low[10], 0, High[0], 10, High[10] + 5 * TickSize);` |
| **dtd** | `Draw.TriangleDown(this, "MyTriangleDown", false, 0, High[0] + 2 * TickSize, Brushes.Red);` |
| **dtu** | `Draw.TriangleUp(this, "MyTriangleUp", false, 0, Low[0] - 2 * TickSize, Brushes.Blue);` |
| **dv** | `Draw.VerticalLine(this, "MyVerticalLine", 0, Brushes.Blue);` |

## [How to insert Code Snippets via the mouse or F2 key](https://developer.ninjatrader.com/docs/desktop/code_snippets\#how-to-insert-code-snippets-via-the-mouse-or-f2-key)

### Using the keyboard

Enter the text in the left column and press the "Tab" key within the NinjaScript Editor.

| **cb** | `CurrentBar` |
| **o** | `Open[0]` |
| **h** | `High[0]` |
| **l** | `Low[0]` |
| **v** | `Volume[0]` |
| **i** | `Input[0]` |

### Previous Bar Values

| **c1** | `Close[1]` |
| **o1** | `Open[1]` |
| **h1** | `High[1]` |
| **l1** | `Low[1]` |
| **v1** | `Volume[1]` |
| **i1** | `Input[1]` |

| Right mouse click in the NinjaScript Editor and select the menu name "Insert Code Snippet" | A menu will display all available code snippets. |

## [Code Snippets](https://developer.ninjatrader.com/docs/desktop/code_snippets\#code-snippets)

Code Snippets can provide you with useful code templates to speed up your coding process.

## [Understanding Code Snippet shortcuts](https://developer.ninjatrader.com/docs/desktop/code_snippets\#understanding-code-snippet-shortcuts)

| Shortcut | Method Signature |
| --- | --- |
| **dap** | `Draw.AndrewsPitchfork(this, "MyAndrewsPitchfork", false, 10, Close[10], 5, High[5], 0, Low[5], Brushes.Blue, DashStyleHelper.Solid, 1);` |
| **da** | `Draw.Arc(this, "MyDrawArc", false, 10, Close[10], 0, Close[0], Brushes.LimeGreen, DashStyleHelper.Dot, 2);` |
| **dd** | `Draw.ArrowDown(this, "MyArrowDown", false, 0, High[0], Brushes.Red);` |
| **du** | `Draw.ArrowUp(this, "MyArrowUp", false, 0, Low[0], Brushes.Red);` |
| **ddi** | `Draw.Diamond(this, "MyDiamond", false, 0, High[0] + 2 * TickSize, Brushes.Blue);` |
| **dt** | `Draw.Dot(this, "MyDot", false, 0, High[0] + 2 * TickSize, Brushes.Blue);` |
| **de** | `Draw.Ellipse(this, "MyEllipse", 10, Low[10], 0, High[0], Brushes.Blue);` |
| **di** | `Draw.ExtendedLine(this, "MyExtendedLine", 10, Close[10], 0, Close[0], Brushes.Blue);` |
| **dfc** | `Draw.FibonacciCircle(this, "MyFibonacciCircle", true, 10, Close[10], 0, Close[0]);` |
| **dfe** | `Draw.FibonacciExtensions(this, "MyFibonacciExtensions", true, 15, Close[15], 10, Close[10], 5, Close[5]);` |
| **dfr** | `Draw.FibonacciRetracements(this, "MyFibonacciRetracements", false, 10, Close[10], 0, Close[0]);` |
| **dft** | `Draw.FibonacciTimeExtensions(this, "MyFibonacciTimeExtensions", false, 10, Close[10], 0, Close[0]);` |
| **dg** | `Draw.GannFan(this, "MyGannFan", true, 10, Close[10]);` |
| **dh** | `Draw.HorizontalLine(this, "MyHorizontalLine", Close[0], Brushes.Blue);` |
| **dl** | `Draw.Line(this, "MyLine", 10, Close[10], 0, Close[0], Brushes.Blue);` |
| **dy** | `Draw.Ray(this, "MyRay", 10, Close[10], 0, Close[0], Brushes.Blue);` |
| **dr** | `Draw.Rectangle(this, "MyRectangle", 10, Low[10], 0, High[0], Brushes.Blue);` |
| **dre** | `Draw.Region(this, CurrentBar, 0, Bollinger(2, 14).Upper, Bollinger(2, 14).Lower, Brushes.Green, Brushes.Blue, 50);` |
| **drx** | `Draw.RegionHighlightX(this, "MyRegionHighlightX", 10, 0, Brushes.Blue);` |
| **dry** | `Draw.RegionHighlightY(this, "MyRegionHighlightY", High[0], Low[0], Brushes.Blue, Brushes.Green, 20);` |
| **drr** | `Draw.RiskReward(this, "MyRiskReward", false, 0, High[0], 10, Low[0], 2, true);` |
| **dru** | `Draw.Ruler(this, "tag1", true, 4, Low[4], 3, High[3], 1, Low[1]);` |
| **ds** | `Draw.Square(this, "MySquare", false, 0, High[0] + 2 * TickSize, Brushes.Blue);` |
| **dx** | `Draw.Text(this, "MyText", "Sample text ", 0, High[0] + 2 * TickSize, Brushes.Blue);` |
| **dxf** | `Draw.TextFixed(this, "MyTextFixed", "Text to draw", TextPosition.TopRight);` |
| **dtc** | `Draw.TrendChannel(this, "TrendChannel", true, 10, Low[10], 0, High[0], 10, High[10] + 5 * TickSize);` |
| **dtd** | `Draw.TriangleDown(this, "MyTriangleDown", false, 0, High[0] + 2 * TickSize, Brushes.Red);` |
| **dtu** | `Draw.TriangleUp(this, "MyTriangleUp", false, 0, Low[0] - 2 * TickSize, Brushes.Blue);` |
| **dv** | `Draw.VerticalLine(this, "MyVerticalLine", 0, Brushes.Blue);` |

## [How to insert Code Snippets via the mouse or F2 key](https://developer.ninjatrader.com/docs/desktop/code_snippets\#how-to-insert-code-snippets-via-the-mouse-or-f2-key)

### Using the keyboard

Enter the text in the left column and press the "Tab" key within the NinjaScript Editor.

| **cb** | `CurrentBar` |
| **o** | `Open[0]` |
| **h** | `High[0]` |
| **l** | `Low[0]` |
| **v** | `Volume[0]` |
| **i** | `Input[0]` |

### Previous Bar Values

| **c1** | `Close[1]` |
| **o1** | `Open[1]` |
| **h1** | `High[1]` |
| **l1** | `Low[1]` |
| **v1** | `Volume[1]` |
| **i1** | `Input[1]` |

| Right mouse click in the NinjaScript Editor and select the menu name "Insert Code Snippet" | A menu will display all available code snippets. |