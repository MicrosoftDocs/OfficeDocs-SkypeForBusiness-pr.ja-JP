---
title: 既知の問題
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 4/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: M365-voice
description: マイクロソフト チーム ルームでは、機能分野別の既知の問題について説明します。
ms.openlocfilehash: d71b209784f4737ac4433e2eececb1f9ada3ebc8
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/30/2019
ms.locfileid: "31013088"
---
# <a name="known-issues"></a>既知の問題 
 
この資料では、マイクロソフト チーム ルームでは、機能分野別の既知の問題が一覧表示されます。
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"> </a>  
## <a name="update"></a>更新 

| 問題のタイトル |  動作\/現象 | 既知の回避策 | KB 資料 |
|  ---        |      ---             |   ---            | --- |
|  最新のアプリケーション         |    マイクロソフト チームの会議室のコンソールは、「最新のシステム構成」のエラーを示しています。                |   [マイクロソフト チームの会議室の回復ツールを使用します。](recovery-tool.md)             |  なし |


<a name="OS-conflicts"> </a>  
## <a name="user-interface"></a>ユーザー ・ インタ フェース 

| 問題のタイトル |  動作\/現象 | 既知の回避策 | KB 資料 |
|  ---        |      ---             |   ---            | --- |
|仮想キーボードがありません。   | マイクロソフト チームの会議室に情報を入力したい場合に、仮想キーボードが表示されません。 Surface Pro の 4 チームの会議室を Microsoft を実行している Windows の 10 の作成者の更新プログラム (バージョン 1703) をインストールした後、この問題が発生します。 | この問題を回避するには、仮想キーボードを手動で開きます。 これを行うには、次の手順を実行します。<br><br> **1。** と、タスク バーを押しながらタップして、**タッチ キーボードを表示する**ボタンです。 キーボードのアイコンがタスク バーの右側に表示されます。 <br><br> **2**は、仮想キーボードを開く [キーボード] アイコンをタップします。 | [KB4037694](https://support.microsoft.com/en-us/help/4037694/virtual-keyboard-missing-in-skype-room-systems-v2) | 
   

<a name="Hardware"> </a>  
## <a name="hardware"></a>ハードウェア

| 問題のタイトル |  動作\/現象 | 既知の回避策 | KB 資料 |
|  ---        |      ---             |   ---            |   --- |
| モニターが検出されません。 | Surface Pro (モデル 2017) デバイスの Microsoft チームの会議室を実行すると、モニターは検出されません。 |  20 以上の秒の Surface Pro の電源ボタンを押しします。 これを行うには、デバイスが再起動し、グラフィックスのキャッシュをクリアします。 |[KB4055681](https://support.microsoft.com/en-us/help/4055681/monitors-are-not-detected-when-you-run-skype-room-systems-on-a-surface)       | 
          
<a name="Limits"> </a>
## <a name="limitations-and-expected-behaviors"></a>制限と予想される動作
***
マイクロソフト チームの会議室が確認されましたが、HDCP の入力をサポートしていません HDMI に問題が発生する機能 (ビデオ、オーディオ) を取り込みます。 マイクロソフト チームのルームに接続されているスイッチが HDCP 機能をオフにできるように注意してください。 
***
屋内ディスプレイの前面として使用される消費者向け TV では、スタンバイ モードからアクティブなビデオ ソースに自動的に切り替わるように、HDMI の CEC (Consumer Electronics Control) 機能をサポート/有効にする必要があります。 この機能はすべての TV でサポートされるものではありません。 
***
必要な帯域幅を確保するために、1 Gbps のワイヤード (有線) ネットワークの接続を常に使用します。 
***
マイクロソフト チーム室デバイス (たとえば、ドメインからドメインに参加しては、その後マイクロソフト チームの会議室を削除する場合) ドメインとの信頼できない場合、デバイスを認証し、設定を開くことはできません。 回避策として、ローカル管理アカウントでログインできます。 
***
マイクロソフト チームの会議室では、エディション (英語、バージョン 1607) はサポートされていません、Windows 10 企業の記念日の 64 ビット バージョンは、3.0.12.0 を解放します。 
***

<a name="See"> </a>  
## <a name="see-also"></a>関連項目

[マイクロソフト チームの会議室のヘルプ](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[マイクロソフト チームの会議室を管理します。](skype-room-systems-v2.md)