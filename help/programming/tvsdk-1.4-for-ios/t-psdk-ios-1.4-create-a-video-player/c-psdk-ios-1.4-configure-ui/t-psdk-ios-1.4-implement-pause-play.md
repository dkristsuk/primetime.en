---
description: You can set up buttons that call TVSDK methods to pause and play the media.
seo-description: You can set up buttons that call TVSDK methods to pause and play the media.
seo-title: Implement a play/pause button
title: Implement a play/pause button
uuid: eccdce4b-0114-4389-b5ee-74fe62d38ed8
---

# Implement a play/pause button{#implement-a-play-pause-button}

You can set up buttons that call TVSDK methods to pause and play the media.

  Use the following sample code to implement a play or pause button:

<!--<a id="example_BC2632D673FE451190A30A23145090D0"></a>-->

```
_playPauseButton =  
[[UIButton alloc] initWithFrame:CGRectMake(BUTTON_POS_X, BUTTON_POS_Y, BUTTON_SIZE_W, BUTTON_SIZE_H)]; 
[_playPauseButton setImage:[UIImage imageNamed:@"play.png"] forState:UIControlStateNormal];  
[_playPauseButton setImage:[UIImage imageNamed:@"pause.png"] forState:UIControlStateSelected]; 
[_playPauseButton addTarget:self action:@selector(playTouch:) forControlEvents:UIControlEventTouchUpInside]; 
[self addSubview:_playPauseButton]; 
 
... 
 
- (void)playTouch:(id)sender { 
    if (self.player.status == PTMediaPlayerStatusPlaying) { 
        _playPauseButton.selected = YES;  
        [self.player pause]; 
    } 
    else { 
        _playPauseButton.selected = NO; [self.player play]; 
    } 
} 

```

