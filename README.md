# Altair In Reflex

The syntax we are shooting for is similar to plotly. https://reflex.dev/docs/library/graphing/other/plotly/ where was passed in the full Altair chart. 

 
``` python
import altair as alt

altair_chart = alt.Chart(cars).mark_point().encode(
    x='Horsepower',
    y='Miles_per_Gallon',
    color='Origin',
).interactive()    margin=dict(l=65, r=50, b=65, t=90),
)


def some_chart():
    return rx.center(
        rx.altair(chart=altair_chart),
    )
```

## Additionally the Chart should work with State

You may need to add a serializer for the altar figure 

See the example here of Serliazer for plotly:
https://github.com/reflex-dev/reflex/blob/1131caebe825f4266856ab7ca73fb76f0490c1e6/reflex/utils/serializers.py#L398-L411

As well as a further reference as to how we wrapped plotly https://github.com/reflex-dev/reflex/blob/main/reflex/components/plotly/plotly.py#L258
