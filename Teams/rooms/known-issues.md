---
title: 既知の問題
ms.author: czawideh
author: cazawideh
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
description: 更新、ユーザー インターフェイス、ハードウェアMicrosoft Teams想定される動作など、Microsoft Teams Rooms の既知の問題について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9472a9cf76f7471d84adea6c8fab58f8d026bcb9
ms.sourcegitcommit: e97c981489ff1f02674df57426da3b22cc6d68c1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/04/2022
ms.locfileid: "63062481"
---
# <a name="known-issues"></a>既知の問題 
 
この記事では、Microsoft Teams Rooms の既知の問題を、機能の領域ごとにまとめています。
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"> </a>  
## <a name="update"></a>更新する 

| 問題のタイトル |  動作 \/ 症状 | 既知の回避策 | サポート技術情報記事 |
|  ---        |      ---             |   ---            | --- |
| ホワイトボード/コンテンツ カメラがエッジが検出されないとコンテンツを強化できない | 4.11.12.0 に更新した後、コンテンツ カメラのビューにホワイトボード エッジがない場合、カメラはカメラのビューですべてのコンテンツを拡張/オーバーレイする必要はありません。| この問題の修正プログラムは、アプリケーション バージョン 4.11.17.0 で利用できます。 | なし |
| Edge ブラウザーの自動起動 | ビルド 97.0.1072.62 より前の Edge ブラウザーは、デバイスの起動時に Microsoft Teams Room アプリと共に自動的に起動します。 | これは自動的に解決され、2022 年 1 月 17 日 (月曜日) 以前のユーザー操作は必要ありません。 より高速な解決が必要な場合は、Edge が Microsoft Teams Room と共に起動すると、URL edge://settings/help にアクセスすると、更新プログラムが自動的にダウンロードされ、適用されます。 更新プログラムの適用が完了したら、ブラウザーで [再起動] を選択します。 Edge Azure IoT閉じ、システムを再起動すると、問題が解決されます。 | なし |
| ギャラリー参加者の分割ビデオ   |  9 人を超えるリモート参加者を含む会議に共有コンテンツがない場合に、会議がデュアル フロント オブ 会議室表示モードの場合、セルフプレビューを含む会議室の前面表示に 1 つのビデオが音声として表示される場合があります。 また、オーディオ参加者の数が実際よりも少ない場合は、デュアル フロント オブ ルーム ディスプレイに表示されます。 | 問題は今後の更新で解決される予定です。 | なし |
| アプリケーションが起動しない |  アプリケーション バージョン 4.4.41.0 に更新した後、システムは黒い画面で起動するか、数分後にサインイン画面に移動します。 | この問題を修正するには、[バージョン 4.4.41.0 に更新後に Microsoft Teams Rooms が起動しない](/microsoftteams/troubleshoot/teams-administration/teams-rooms-app-wont-start-after-update) の手順に従います。  | なし |
|  コンテンツ共有後の会議の量が少ない         |   Microsoft Teams 20H2 の会議室デバイスでは、Windows 10 HDMI 経由でコンテンツを共有した後、メディアと会議の音量が低下します。 これは、20H2 のオーディオの問題Windows 10発生します。 | この問題の修正プログラムは、アプリケーション バージョン [4.9.12.0 で利用できます](/microsoftteams/rooms/rooms-release-note#49120-7282021)。 | なし |
|  旧版のアプリ         |    Microsoft Teams Rooms のコンソールには、「システム構成が古くなっています」というエラーが表示されます。                |   [Microsoft Teams Rooms の回復ツールを使用する](recovery-tool.md)             |  なし |
|  デバイスを Windows 10 でサポートされていないバージョンに更新した   |    Windows 10 デバイスはバージョン 1803 からバージョン 1809 に更新されましたが、これはサポートされていないバージョンです。 サポートされているバージョンは 1903 です。 |   これは、[DeferFeatureUpdatesPeriodinDays 向けグループ ポリシーまたは MDM 設定](/windows/deployment/update/waas-configure-wufb)で、機能の更新を指定した日数 (最大 365 日) 保留にした場合に発生することがあります。 <br><br> Windows 10 バージョン 1903 は Microsoft Teams Rooms でサポートされていますが、バージョン 1809 はサポートされていません。 ただし、2020 年 3 月 27 日時点で、バージョン 1809 はリリースから 365 日以上経過しています。 この設定が変更されていない場合は、Windows は バージョン 1809 のインストールを試行します。これにより、Microsoft Teams Rooms で問題が発生する可能性があります。<br><br>このような状況を回避するには、更新を保留しているグループ ポリシーまたは MDM 設定のいずれかを **削除** します。 これにより、Windows はサポートされている最新の OS バージョンに更新されます。 <br><br>**大事な：** グループ ポリシーまたは MDM 設定は **削除する必要** があります (未構成の状態)。 **0 に設定することはできません**。 ポリシーが 0 に設定された場合、Windows はサポートされていない可能性がある使用可能な最新バージョンを選択します。 |  なし |



<a name="OS-conflicts"> </a>  
## <a name="user-interface"></a>ユーザー インターフェイス 

| 問題のタイトル |  動作 \/ 症状 | 既知の回避策 | サポート技術情報記事 |
|  ---        |      ---             |   ---            | --- |
|仮想キーボードが見つかりません   | Microsoft Teams Rooms に情報を入力する必要がある場合に、仮想キーボードが表示されません。 この問題は、Windows 10 のバージョン 1903 で発生します。 | Windows 更新プログラムを使用して、x64 ベース システム用 Windows 10 バージョン 1903 の累積的な更新プログラム 2020-04 をインストールします。  | なし | 

<a name="Hardware"> </a>  
## <a name="hardware"></a>ハードウェア

| 問題のタイトル |  動作 \/ 症状 | 既知の回避策 | サポート技術情報記事 |
|  ---        |      ---             |   ---            |   --- |
| モニターが検出されません | Surface Pro (2017 年版モデル) のデバイスで Microsoft Teams Rooms を実行すると、モニターは検出されません。 |  20 秒以上 Surface Pro の電源ボタンを長押しします。 長押しすると、デバイスが再起動し、グラフィックのキャッシュをクリアします。 |[KB4055681](https://support.microsoft.com/help/4055681/monitors-are-not-detected-when-you-run-skype-room-systems-on-a-surface)       | 

<a name="Limits"> </a>
## <a name="limitations-and-expected-behaviors"></a>制限事項と予想される動作

***

[最前面] ディスプレイのレイアウト ピッカーでは、最前面行が "プレビュー" としてマークされます。 今後、さらに多くの機能と改善が追加される予定です。 リリース後に対処するには、次の制限があります。

- 最前面のレイアウトは、1 つのディスプレイの前面に最大 4 人のビデオ参加者を表示します。 デュアル フロント オブ ルームに最大 9 つのビデオが表示されます。 これらの参加者は、最後にアクティブなスピーカーから選択されます。

- 最前面行には、100% のスケーリングで 1080p ディスプレイが必要です。 部屋の前面の表示のフォント サイズが小さすぎたり、部屋の必要性に応じて大きすぎた[](rooms-operations.md#change-scale-and-resolution)りする場合は、「部屋の前面のスケールと解像度を変更する」を参照して、表示設定を調整します。

***

Microsoft Teams Rooms は、HDMI インジェストの機能 (ビデオ、オーディオ) に関する問題を引き起こすことが確認されている、HDCP 入力をサポートしていません。 Microsoft Teams Rooms に接続されたスイッチの HDCP オプションがオフになっていることを必ず確認してください。 

***

スタンバイ モードからソースが起動した場合に、ルーム前面のディスプレイをアクティブなビデオ ソース (例: オン) に自動的に切り替える場合は、特定の条件を満たしている必要があります。 この機能はオプションですが、基盤となるハードウェアで機能がサポートされている場合は、Microsoft Teams Rooms ソフトウェアによってサポートされます。 ルームの前方ディスプレイとして使用される一般向けテレビは、HDMI の CEC (Consumer Electronics Control) 機能をサポートしている必要があります。  選択したドックまたは本体によっては、目的の動作を有効にするには、クセロンの [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) や [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) などのコントローラーが必要になる場合があります。 ドックまたは本体が CEC をサポートしている場合は、製造元のサポート ドキュメントを参照してください。

さらに、ルーム ディスプレイの前面として使用されるコンシューマーテレビは、Microsoft Teams Rooms ソフトウェアの安定性の問題を引き起こす可能性があります。 これは、スタンバイ モードの一貫性のない実装、アクティブなビデオ ソースの選択、および障害のある EDID 情報を Microsoft Teams Rooms デバイスに伝達するために発生します。 既知の症状は、会議室ディスプレイの前面に黒/灰色の画面が表示される場合や、Microsoft Teams 会議室本体がスタンバイから目を覚ますと応答しなくなる場合です。  コンシューマーテレビを使用するときに問題が発生する場合は、構成可能な EDID コントローラーまたは EDID エミュレーター (FsR Video Products Group から、クセロンまたは [DR-EDID Emulator](https://fsrinc.com/fsr-products/product/dr-edid-manager-learner/category_pathway-143) から [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) など) をインストールすることをお勧めします。

***

常に有線の 1-Gbps ネットワーク接続を使用して、必要な帯域幅を確保してください。 

***

Microsoft Teams Rooms デバイスとドメインとの信頼が途絶えている場合は、デバイスに認証して [設定] を開くことはできません。 たとえば、ドメインに参加した後に、そのドメインから Microsoft Teams Rooms を削除した場合、信頼関係が失われます。 回避策では、ローカルの管理者アカウントでログインします。 
***
Microsoft Teams Rooms は、マルチウィンドウ アプリケーションであり、アプリが正常に機能するために、ルームの前方ディスプレイをデバイスの HDMI ポートに接続する必要があります。 テスト中で、まだディスプレイを購入していない場合は、HDMI ディスプレイを接続するか、ダミーの HDMI プラグを使用するかのいずれかを必ず実行してください。
***
<a name="See"> </a>  
## <a name="see-also"></a>関連項目

[Microsoft Teams Rooms ヘルプ](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams Rooms を管理する](rooms-manage.md)
