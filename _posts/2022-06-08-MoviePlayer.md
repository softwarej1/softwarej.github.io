---

layout: single
classes: wide
title:  "14장 스위프트 과제"
---

# 비디오 재생 앱 만들기

{: .notice--info}

**[공지사항]**[스위프트 과제 다운로드 주소 이동.](https://github.com/softwarej1/Swift_source_code/)



```swift
/
//  ViewController.swift
//  MoviePlayer
//
//  Created by 203a18 on 2022/05/27.
//

import UIKit
import AVKit

class ViewController: UIViewController {

    override func viewDidLoad() {
        super.viewDidLoad()
        // Do any additional setup after loading the view.
    }

    @IBAction func btnplayInternalMovie(_ sender: UIButton) {
        
        let filePath:String? = Bundle.main.path(forResource: "FastTyping", ofType: "mp4")
        let url = NSURL(fileURLWithPath: filePath!)
        
        playVidio(url: url)
        
        let playerController = AVPlayerViewController()
        
        let player = AVPlayer(url: url as URL)
        playerController.player = player
        
        self.present(playerController, animated: true)
        {
            player.play()
        }
    }
    
    @IBAction func btnPlayerExternalMovie(_ sender: UIButton) {
     
        let url = NSURL(string: "https://dl.dropboxusercontent.com/s/e38auz050w2mvud/fireworks.mp4")!
        
        playVidio(url: url)
        
        let playerController = AVPlayerViewController()
        
        let player = AVPlayer(url: url as URL)
        playerController.player = player
        
        self.present(playerController, animated: true){
            player.play()
        }
    }
    
    private func playVidio(url: NSURL){
        let playerConntroller = AVPlayerViewController()
        
        let player = AVPlayer(url: url as URL)
        playerConntroller.player = player
        
        self.present(playerConntroller, animated: true){
            player.play()
        }
    }
    
}
```

