
## Installation

```sh
npm install react-native-flashdrag-list
`` "react-native-flashdr
  title: string,
  color: string
}

const NUM_ITEMS = 200
const ITEM_HEIGHT = 60

const App = () => {

  const [ data, setData ] = useState(() => {
    return new Array(NUM_ITEMS).fill("").map((_, i) => {
      const colors = [
        '#493548',
        '#4B4E6D',
        '#6A8D92',
        '#80B192',
        '#A1E887'
      ]
      return {
        title: "Item " + i,
        color: colors[Math.round(i % colors.length)]
      }
    }) as Array<Item>
  })

  const onSort = (fromIndex: number, toIndex: number) => {
    const copy = [...data]
    const removed = copy.splice(fromIndex, 1)
    copy.splice(toIndex, 0, removed[0]!)
    setData(copy)
  }

  const renderItem = (
    item: Item,
    index: number,
    active: boolean,
    beginDrag: () => any
  ) => {
    return (
      <TouchableOpacity
        onLongPress={beginDrag}
        style={{
          width: '100%',
          height: ITEM_HEIGHT,
          alignItems: 'center',
          justifyContent: 'center',
          backgroundColor: item.color
        }}
      >
        <Text
          style={{
            color: 'white',
            fontWeight: 'bold'
          }}
          key={index}
        >{item.title}</Text>
      </TouchableOpacity>
    )
  }

  return (
    <G
          data={data}
          renderItem={renderItem}
          itemsSize={ITEM_HEIGHT}
        />
      </SafeAreaView>
    </GestureHandlerRootView>
  )
}

export default App

```

low
---

Made with [create-react-n
