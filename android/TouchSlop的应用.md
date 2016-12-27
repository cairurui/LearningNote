### 在onTouchEvent中作点击事件

```

	private int lastX = -1;
	private int lastY = -1;
	private long mLastTime;

	@Override
	public boolean onTouchEvent(MotionEvent event) {
		switch (event.getActionMasked()) {
		case MotionEvent.ACTION_DOWN:
			lastX = (int) event.getX();
			lastY = (int) event.getY();
			mLastTime = System.currentTimeMillis();
			break;

		case MotionEvent.ACTION_MOVE:
		  ...
			break;
		case MotionEvent.ACTION_UP:
			int x = (int) event.getX();
			int y = (int) event.getY();
			int slop = ViewConfiguration.get(getContext()).getScaledTouchSlop();
      boolean isLongPress = System.currentTimeMillis() - mLastTime >1*1000;

			if ((slop > Math.abs(lastX - x)) && (slop > Math.abs(lastY) - y) && !isLongPress) {
				performClick();
			}
			break;
		}
		return true;
	}

```
