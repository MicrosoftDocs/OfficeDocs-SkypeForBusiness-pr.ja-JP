---
title: 既知の問題
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 4/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: この資料では、機能分野別の Skype ルーム システム v2 の既知の問題について説明します。
ms.openlocfilehash: 2fde12d616260963dc342df2d9cef94acf616756
ms.sourcegitcommit: dc7a7da270121c3702f38614158c9067ad38f12a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/14/2018
ms.locfileid: "19881543"
---
# <a name="known-issues"></a>既知の問題 
 
この資料では、機能分野別の Skype ルーム システム v2 の既知の問題が一覧表示されます。
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"> </a>  
## <a name="update"></a>更新 

| 懸案事項のタイトル |  動作\/現象 | 既知の回避策 | KB 資料 |
|  ---        |      ---             |   ---            | --- |
|  最新のアプリケーション         |    Skype ルーム システム v2 のコンソールは、「最新のシステム構成」のエラーを示しています。                |   [Skype ルーム システム v2 の回復ツールを使用します。](recovery-tool.md)             |  なし |


<a name="OS-conflicts"> </a>  
## <a name="user-interface"></a>ユーザー ・ インタ フェース 

| 懸案事項のタイトル |  動作\/現象 | 既知の回避策 | KB 資料 |
|  ---        |      ---             |   ---            | --- |
|仮想キーボードがありません。   | Skype ルーム システム v2 に情報を入力したい場合に、仮想キーボードが表示されません。 Skype ルーム システムのバージョン 2 を実行している Surface Pro 4 の Windows の 10 の作成者の更新プログラム (1703 のバージョン) をインストールした後、この問題が発生します。 | この問題を回避するには、仮想キーボードを手動で開きます。 これを行うには、次の手順を実行します。<br><br> **1。** と、タスク バーを押しながらタップして、**タッチ キーボードを表示する**ボタンです。 キーボードのアイコンがタスク バーの右側に表示されます。 <br><br> **2**は、仮想キーボードを開く [キーボード] アイコンをタップします。 | [KB4037694](https://support.microsoft.com/en-us/help/4037694/virtual-keyboard-missing-in-skype-room-systems-v2) | 
   

<a name="Hardware"> </a>  
## <a name="hardware"></a>ハードウェア

| 懸案事項のタイトル |  動作\/現象 | 既知の回避策 | KB 資料 |
|  ---        |      ---             |   ---            |   --- |
| モニターが検出されません。 | Surface Pro (モデル 2017) デバイスに Skype ルーム システム v2 を実行すると、モニターは検出されません。 |  20 以上の秒の Surface Pro の電源ボタンを押しします。 これを行うには、デバイスが再起動し、グラフィックスのキャッシュをクリアします。 |[KB4055681](https://support.microsoft.com/en-us/help/4055681/monitors-are-not-detected-when-you-run-skype-room-systems-on-a-surface)       | 
          
<a name="Limits"> </a>
## <a name="limitations-and-expected-behaviors"></a>制限と予想される動作
***
V2 は HDMI での問題を引き起こすことが確認されています、HDCP の入力をサポートしていません、Skype ルーム システムは、機能 (ビデオ、オーディオ) を取り込みします。 Skype ルーム システム v2 に接続されたスイッチが HDCP 機能をオフにできるように注意します。 
***
屋内ディスプレイの前面として使用される消費者向け TV では、スタンバイ モードからアクティブなビデオ ソースに自動的に切り替わるように、HDMI の CEC (Consumer Electronics Control) 機能をサポート/有効にする必要があります。 この機能はすべての TV でサポートされるものではありません。 
***
必要な帯域幅を確保するために、1 Gbps のワイヤード (有線) ネットワークの接続を常に使用します。 
***
Skype ルーム システム v2 デバイスで (たとえば、ドメインからドメインに参加しては、その後 Skype ルーム システム v2 を削除する場合) ドメインとの信頼関係が失われた場合にデバイスを認証し、設定を開くことはできません。 回避策として、ローカル管理アカウントでログインできます。 
***
Skype ルーム システム v2 リリース 3.0.12.0 は、Windows 10 企業の記念日の版 (英語、1607 のバージョン) の 64 ビット バージョンがサポートされていません。 
***

<a name="See"> </a>  
## <a name="see-also"></a>この手順は役に立ちましたか? 役に立った場合は、この記事の下でお知らせください。役に立たなかった場合は、わかりにくかった部分をお知らせください。いただいたフィードバックを元に手順を再確認します。

[Skype ルーム システムのバージョン 2 のヘルプ](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Skype ルームの管理システム v2](skype-room-systems-v2.md)