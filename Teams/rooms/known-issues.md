---
title: 既知の問題
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
description: 管理者は、更新、ユーザーインターフェイス、ハードウェア、制限事項、予期される動作など、Microsoft Teams のルームの既知の問題のリストについて知ることができます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1083ceb040f173aeef0a8a60d56a888a6b8fdb17
ms.sourcegitcommit: 02dd624d39a14f48b9d2463881605d2f051722e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/25/2020
ms.locfileid: "44874454"
---
# <a name="known-issues"></a>既知の問題 
 
この記事では、Microsoft Teams Rooms の既知の問題を、機能の領域ごとにまとめています。
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"> </a>  
## <a name="update"></a>更新する 

| 問題のタイトル |  動作 \/ 症状 | 既知の回避策 | サポート技術情報記事 |
|  ---        |      ---             |   ---            | --- |
| アプリケーションが起動しない |  アプリケーションバージョン4.4.41.0 に更新した後、システムは黒い画面で起動するか、数分後にログオン画面に移動します。 | この問題を解決するために、 [Microsoft Teams 会議室アプリケーションは、バージョン4.4.41.0 への更新後は開始されません](https://docs.microsoft.com/microsoftteams/troubleshoot/teams-administration/teams-rooms-app-wont-start-after-update)。  | なし |
|  旧版のアプリ         |    Microsoft Teams Rooms のコンソールには、「システム構成が古くなっています」というエラーが表示されます。                |   [Microsoft Teams Rooms の回復ツールを使用する](recovery-tool.md)             |  なし |
|  サポートされていないバージョンの Windows 10 に更新されたデバイス   |    Windows 10 デバイスがバージョン1803からバージョン1809に更新されました。これはサポートされていません。 サポートされているバージョンは1903です。 |   この問題は、 [DeferFeatureUpdatesPeriodinDays 設定のグループポリシーまたは MDM の設定](https://docs.microsoft.com/windows/deployment/update/waas-configure-wufb)によって、指定した日数の機能更新プログラムを延期できる場合に、最大365日間に設定されている場合に発生する可能性があります。 <br><br> Windows 10 バージョン1809は、Microsoft Teams のルームでサポートされていません。バージョン1903はサポートされています。 ただし、2020年3月27日より、バージョン1809は365日以上経過しています。 この設定が変更されていない場合、Windows はバージョン1809をインストールしようとします。これにより、Microsoft Teams のルームで問題が発生する可能性があります。<br><br>この問題を回避するには、更新を延期するグループポリシーまたは MDM 設定を**削除**します。 これにより、Windows はサポートされている最新の OS バージョンに更新されます。 <br><br>**重要**グループポリシーまたは MDM 設定は**削除**する必要があり (左側に構成されて**いない)、0には設定しない**でください。 ポリシーが0に設定されている場合、Windows はサポートされていない最新バージョンを使用します。 |  なし |



<a name="OS-conflicts"> </a>  
## <a name="user-interface"></a>ユーザー インターフェイス 

| 問題のタイトル |  動作 \/ 症状 | 既知の回避策 | サポート技術情報記事 |
|  ---        |      ---             |   ---            | --- |
|仮想キーボードが見つかりません   | Microsoft Teams Rooms に情報を入力する必要がある場合に、仮想キーボードが表示されません。 この問題は、Windows 10 バージョン1903で発生します。 | Windows の更新プログラムを使用して、x64 ベースのシステム用の Windows 10 バージョン1903の2020-04 累積更新プログラムをインストールします。  | なし | 

<a name="Hardware"> </a>  
## <a name="hardware"></a>ハードウェア

| 問題のタイトル |  動作 \/ 症状 | 既知の回避策 | サポート技術情報記事 |
|  ---        |      ---             |   ---            |   --- |
| モニターが検出されません | Surface Pro (2017 年版モデル) のデバイスで Microsoft Teams Rooms を実行すると、モニターは検出されません。 |  20 秒以上 Surface Pro の電源ボタンを長押しします。 長押しすると、デバイスが再起動し、グラフィックのキャッシュをクリアします。 |[KB4055681](https://support.microsoft.com/help/4055681/monitors-are-not-detected-when-you-run-skype-room-systems-on-a-surface)       | 

<a name="Limits"> </a>
## <a name="limitations-and-expected-behaviors"></a>制限事項と予想される動作

***

Microsoft Teams Rooms は、HDMI インジェストの機能 (ビデオ、オーディオ) に関する問題を引き起こすことが確認されている、HDCP 入力をサポートしていません。 Microsoft Teams Rooms に接続されたスイッチの HDCP オプションがオフになっていることを必ず確認してください。 

***

ルームの前方ディスプレイを、ソースがスタンバイ モードから復帰したときにアクティブなビデオ ソース (MTR コンソールなど) に自動的に切り替える場合は、特定の条件を満たしている必要があります。 この機能はオプションですが、基盤となるハードウェアで機能がサポートされている場合は、Microsoft Teams ミーティング ソフトウェアによってサポートされます。 ルームの前方ディスプレイとして使用される一般向けテレビは、HDMI の CEC (Consumer Electronics Control) 機能をサポートしている必要があります。  選択されているドックまたはコンソール (CEC をサポートしていない可能性があるため、製造元のサポート ドキュメントを参照してください) に応じて、適切な動作を実現するには、[Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) などのワークスペース コントローラーが必要になる場合があります。 

***

常に有線の 1-Gbps ネットワーク接続を使用して、必要な帯域幅を確保してください。 

***

Microsoft Teams ミーティング デバイスとドメインとの信頼が途絶えている場合は、デバイスに認証して [設定] を開くことはできません。 たとえば、ドメインに参加した後に、そのドメインから Microsoft Teams ミーティングを削除した場合、信頼関係が失われます。 回避策では、ローカルの管理者アカウントでログインします。 
***
Microsoft Teams ミーティングは、マルチウィンドウ アプリケーションであり、アプリが正常に機能するために、ルームの前方ディスプレイをデバイスの HDMI ポートに接続する必要があります。 テスト中で、まだディスプレイを購入していない場合は、HDMI ディスプレイを接続するか、ダミーの HDMI プラグを使用するかのいずれかを必ず実行してください。
***
<a name="See"> </a>  
## <a name="see-also"></a>関連項目

[Microsoft Teams Rooms ヘルプ](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams Rooms を管理する](rooms-manage.md)
