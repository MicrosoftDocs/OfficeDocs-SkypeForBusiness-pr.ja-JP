---
title: 既知の問題
ms.author: dstrome
author: dstrome
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
description: 管理者は、更新プログラム、ユーザー インターフェイス、ハードウェア、制限事項や想定される動作を含む、Microsoft Teams Rooms の既知の問題のリストについて知ることができます。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 63a646fa6fb404cb46de889c318181146cb44b2a
ms.sourcegitcommit: 2639da2c9f903a9a82866be9db2b69a705c54200
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055739"
---
# <a name="known-issues"></a>既知の問題 
 
この記事では、Microsoft Teams Rooms の既知の問題を、機能の領域ごとにまとめています。
<!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"> </a>  
## <a name="update"></a>更新する 

| 問題のタイトル |  動作 \/ 症状 | 既知の回避策 | サポート技術情報記事 |
|  ---        |      ---             |   ---            | --- |
| アプリケーションが起動しない |  アプリケーション バージョン 4.4.41.0 に更新すると、システムが黒い画面を表示するか、数分後にログオン画面に移動します。 | この問題を修正するには、[バージョン 4.4.41.0 に更新後に Microsoft Teams Rooms が起動しない](https://docs.microsoft.com/microsoftteams/troubleshoot/teams-administration/teams-rooms-app-wont-start-after-update) の手順に従います。  | なし |
|  SfB 会議コンテンツ共有が全画面表示されない         |    Skype for Business の会議で、高解像度の設定を使用して正面表示にした会議室では、コンテンツが会議に共有されている場合にウィンドウの正面に全画面が表示されない問題が発生することがあります。 これは、Windows 10 Remote Desktop Protocol (RDP) API の根底にある問題が原因で発生します。 | この問題を解決するには、`<WinRTRdpEnabled>` XML 設定を使用して、Windows 10 RDP API を無効にします。 無効にするには、値を `false` として指定する必要があります。 詳細については、「[XML 構成ファイルを使用してコンソールの設定を管理する](xml-config-file.md#manage-console-settings-with-an-xml-configuration-file)」を参照してください。 | なし |
|  旧版のアプリ         |    Microsoft Teams Rooms のコンソールには、「システム構成が古くなっています」というエラーが表示されます。                |   [Microsoft Teams Rooms の回復ツールを使用する](recovery-tool.md)             |  なし |
|  デバイスを Windows 10 でサポートされていないバージョンに更新した   |    Windows 10 デバイスはバージョン 1803 からバージョン 1809 に更新されましたが、これはサポートされていないバージョンです。 サポートされているバージョンは 1903 です。 |   これは、[DeferFeatureUpdatesPeriodinDays 向けグループ ポリシーまたは MDM 設定](https://docs.microsoft.com/windows/deployment/update/waas-configure-wufb)で、機能の更新を指定した日数 (最大 365 日) 保留にした場合に発生することがあります。 <br><br> Windows 10 バージョン 1903 は Microsoft Teams Rooms でサポートされていますが、バージョン 1809 はサポートされていません。 ただし、2020 年 3 月 27 日時点で、バージョン 1809 はリリースから 365 日以上経過しています。 この設定が変更されていない場合は、Windows は バージョン 1809 のインストールを試行します。これにより、Microsoft Teams Rooms で問題が発生する可能性があります。<br><br>このような状況を回避するには、更新を保留しているグループ ポリシーまたは MDM 設定のいずれかを **削除** します。 これにより、Windows はサポートされている最新の OS バージョンに更新されます。 <br><br>**重要** グループ ポリシーまたは MDM 設定は、**削除済み** (構成しないままにする) および **0 に設定しない** 必要があります。 ポリシーが 0 に設定された場合、Windows はサポートされていない可能性がある使用可能な最新バージョンを選択します。 |  なし |



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

**_

Microsoft Teams Rooms は、HDMI インジェストの機能 (ビデオ、オーディオ) に関する問題を引き起こすことが確認されている、HDCP 入力をサポートしていません。 Microsoft Teams Rooms に接続されたスイッチの HDCP オプションがオフになっていることを必ず確認してください。 

_*_

ルームの前方ディスプレイを、ソースがスタンバイ モードから復帰したときにアクティブなビデオ ソース (MTR コンソールなど) に自動的に切り替える場合は、特定の条件を満たしている必要があります。 この機能はオプションですが、基盤となるハードウェアで機能がサポートされている場合は、Microsoft Teams Rooms ソフトウェアによってサポートされます。 ルームの前方ディスプレイとして使用される一般向けテレビは、HDMI の CEC (Consumer Electronics Control) 機能をサポートしている必要があります。  選択されているドックまたはコンソール (CEC をサポートしていない可能性があるため、製造元のサポート ドキュメントを参照してください) に応じて、適切な動作を実現するには、Crestron 社の [HD-RX-201-C-E](https://www.crestron.com/Products/Video/HDMI-Solutions/HDMI-Extenders/HD-RX-201-C-E) や Extron 社の [Extron HD CTL 100](https://www.extron.com/article/hdctl100ad) などのコントローラーが必要になる場合があります。 

_*_

常に有線の 1-Gbps ネットワーク接続を使用して、必要な帯域幅を確保してください。 

_*_

Microsoft Teams Rooms デバイスとドメインとの信頼が途絶えている場合は、デバイスに認証して [設定] を開くことはできません。 たとえば、ドメインに参加した後に、そのドメインから Microsoft Teams Rooms を削除した場合、信頼関係が失われます。 回避策では、ローカルの管理者アカウントでログインします。 
_*_ Microsoft Teams Rooms はマルチウィンドウ アプリケーションであり、アプリが正しく機能するためには、デバイスの HDMI ポートに接続する会議室の前面ディスプレイが必要です。 テスト中で、まだディスプレイを購入していない場合は、HDMI ディスプレイを接続するか、ダミーの HDMI プラグを使用するかのいずれかを必ず実行してください。
_** <a name="See"> </a>  
## <a name="see-also"></a>関連項目

[Microsoft Teams Rooms ヘルプ](https://support.office.com/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[Microsoft Teams Rooms を管理する](rooms-manage.md)
