## Widgets

The minimal code:

```typescript
namespace myOrg_myWidget {
    S.registerBuilder("myOrg.myWidget", (w, ctx) => new MyWidget(w, ctx))

    class MyWidget extends S.Widget {
        constructor(w: S.WidgetInfo, ctx: S.BuildContext) {
            super(w, ctx, "myOrg_myWidget")
        }
    }
}
```

