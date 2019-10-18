---
title: 既知の問題
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
ms.date: 4/17/2018
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
ms.collection:
- M365-collaboration
description: この記事では、Microsoft Teams Rooms の既知の問題を、機能の領域ごとに説明しています。
ms.openlocfilehash: 79bebf69c0d4fc8dabff3e294166e7ab08b79166
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/17/2019
ms.locfileid: "37571391"
---
# <a name="known-issues"></a>既知の問題 
 
この記事では、Microsoft Teams Rooms の既知の問題を、機能の領域ごとにまとめています。
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"> </a>  
## <a name="update"></a>更新する 

| 問題のタイトル |  動作 \/ 症状 | 既知の回避策 | サポート技術情報記事 |
|  ---        |      ---             |   ---            | --- |
|  旧版のアプリ         |    Microsoft Teams Rooms のコンソールには、「システム構成が古くなっています」というエラーが表示されます。                |   [Microsoft Teams Rooms の回復ツールを使用する](recovery-tool.md)             |  なし |


<a name="OS-conflicts"> </a>  
## <a name="user-interface"></a>ユーザー インターフェイス 

| 問題のタイトル |  動作 \/ 症状 | 既知の回避策 | サポート技術情報記事 |
|  ---        |      ---             |   ---            | --- |
|仮想キーボードが見つかりません   | Microsoft Teams Rooms に情報を入力する必要がある場合に、仮想キーボードが表示されません。 この問題は、Microsoft Teams Rooms を実行している Surface Pro 4 に Windows 10 Creators Update (バージョン 1703) をインストールした後に発生します。 | この問題を回避するには、仮想キーボードを手動で開きます。 これを行うには、次の手順を実行します。<br><br> **1.** タスク バーをタップして長押しし、[**タッチ キーボードを表示**] ボタンをタップします。 キーボードのアイコンは、タスク バーの右側に表示されます。 <br><br> **2.** 仮想キーボードを開くには、キーボード アイコンをタップします。 | [KB4037694](https://support.microsoft.com/en-us/help/4037694/virtual-keyboard-missing-in-skype-room-systems-v2) | 

<a name="Hardware"> </a>  
## <a name="hardware"></a>ハードウェア

| 問題のタイトル |  動作 \/ 症状 | 既知の回避策 | サポート技術情報記事 |
|  ---        |      ---             |   ---            |   --- |
| モニターが検出されません | Surface Pro (2017 年版モデル) のデバイスで Microsoft Teams Rooms を実行すると、モニターは検出されません。 |  20 秒以上 Surface Pro の電源ボタンを長押しします。 長押しすると、デバイスが再起動し、グラフィックのキャッシュをクリアします。 |[KB4055681](https://support.microsoft.com/en-us/help/4055681/monitors-are-not-detected-when-you-run-skype-room-systems-on-a-surface)       | 

<a name="Limits"> </a>
## <a name="limitations-and-expected-behaviors"></a>制限事項と予想される動作

***

Microsoft Teams Rooms は、HDMI インジェストの機能 (ビデオ、オーディオ) に関する問題を引き起こすことが確認されている、HDCP 入力をサポートしていません。 Microsoft Teams Rooms に接続されたスイッチの HDCP オプションがオフになっていることを必ず確認してください。 

***

会議室の表示の前に、ソースがスタンバイモードから復帰したときに、アクティブなビデオソース (MTR 本体など) に自動的に切り替える場合は、特定の条件を満たしている必要があります。 この機能はオプションですが、基盤となるハードウェアによって機能がサポートされている場合は、Microsoft Teams ルームソフトウェアでサポートされています。 Room ディスプレイの正面に使用されている消費者のテレビでは、HDMI のコンシューマーエレクトロニクス制御 (CEC) 機能をサポートしている必要があります。  選択された dock またはコンソール (CEC をサポートしていない可能性があります) によっては、必要な動作を実現するために、 [HD CTL 100 の extron](https://www.extron.com/article/hdctl100ad)のワークスペースコントローラーが必要になることがあります。 

***

常に有線の 1 Gbps ネットワーク接続を使用して、必要な帯域幅を確保します。 

***

Microsoft Teams の会議室デバイスがドメインと信頼できなくなった場合、デバイスに対して認証することはできません。また、設定を開くこともできません。 たとえば、ドメインが参加した後に、ドメインから Microsoft Teams のルームを削除した場合、信頼は失われます。 回避策では、ローカルの管理者アカウントでログインします。 
***
Windows 10 Enterprise Anniversary エディション (英語版、バージョン 1607) の 64 ビット バージョンは Microsoft Teams Rooms リリース 3.0.12.0 ではサポートされなくなりました。 
***
Microsoft Teams のルームは、複数のウィンドウで表示されるアプリケーションであり、アプリが正常に動作するためには、デバイスの HDMI ポートに接続するために、room ディスプレイの前面が必要です。 テストしていて、ディスプレイをまだ購入していない場合は、HDMI ディスプレイが接続されているか、ダミー HDMI プラグを使用していることを確認してください。
***
Windows 10 1903 は、グラフィックスドライバーの問題により、Crestron に含まれている Microsoft Teams の会議室のデバイスではまだ提供されていません。

***
<a name="See"> </a>  
## <a name="see-also"></a>関連項目

[Microsoft Teams Rooms ヘルプ](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams Rooms を管理する](skype-room-systems-v2.md)
