---
sidebar_position: 7
---

# Patcher
The Patcher is a utility class for patching React Components, required for modifying the user interface.

## Methods
### patch
**patch**(`name: string`, `func: (ReactElement) => ReactElement`): `void`

Patches a mdpkm component with the given function.

#### Example
```js
Patcher.patch('Home', child => ({
    ...child, 
    props: {
        ...child.props,
        children: Patcher.mapRecursive(child => {
            if (child?.type?.name === 'InstanceList')
                return React.cloneElement(child, {
                    onSelect: id => {
                        child.props.onSelect(id);
                        console.log(id);
                    }
                });
            return child;
        }, child.props.children)
    }
}));
```

### patchChild
**patchChild**(`name: string`, `type: string`, `func: (ReactElement) => ReactElement`): `void`

Patches a mdpkm component's descendants with the given function.

#### Example
```js
Patcher.patchChild('Home', 'SideNavigation', child => {
    if (child?.type?.name === 'InstanceList')
        return React.cloneElement(child, {
            onSelect: id => {
                child.props.onSelect(id);
                console.log(id);
            }
        });
    return child;
});
```