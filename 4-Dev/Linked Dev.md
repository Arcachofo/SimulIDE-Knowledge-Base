A Component that wants to link to another components must:
- Derive from Linkable class.
- Implement context menu action ( TODO: add to Component::ContextMenu).
- Implement code to act on linked components.
- Add hidden property "Links".
- - Set m_linkable = true; in constructor.

A component that wants to do something when linked must implement one or both:
void setLinkedValue( double v, int i=0 )
void setLinkedString( QString str, int i=0 )


component.h:
void setLinkedValue( double v, int i=0 )
void setLinkedString( QString str, int i=0 )
void setLinked( bool l )

linkable.h
void createLinks( QList<Component*>* )
void compSelected( Component* comp )

#dev