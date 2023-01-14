---
title: Microsoft Teams Rooms を管理する
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 39d7dc65-22c3-400f-91f1-87ed2fd792b6
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Rooms
description: 継続的なメンテナンスと運用を開発および実行して、Microsoft Teams Rooms システムをユーザーが確実に利用できるようにする方法について説明します。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 36145202e12cd9b987b50efd6de3efe636c86ac2
ms.sourcegitcommit: 1934c4803b5b6ae9b9ccd49e695944446d5d5810
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/14/2023
ms.locfileid: "69806372"
---
# <a name="manage-microsoft-teams-rooms-and-surface-hubs"></a>Microsoft Teams Roomsと Surface Hubs を管理する

組織内にデバイスまたは Surface Hub をMicrosoft Teams Roomsしている場合は、柔軟な管理オプションがあります。  デバイスは、すべての Teams ソリューション (Microsoft Teams 管理センター) を管理する同じ中央の場所で自分で管理できます。

Microsoft Teams 管理センターでは、次のことができます。

- デバイスの再起動やデバイス ログのダウンロードなどのデバイス管理を実行する
- Teams 固有の設定を適用する
- カメラ、ディスプレイ、マイクなど、Microsoft Teams Roomsとその周辺機器の正常性状態を確認する
- 現在と過去のミーティングアクティビティ（通話品質、ネットワークの状態と接続、参加者数など）を確認する
- Microsoft Teams Roomsに接続されている周辺機器 (カメラやプロジェクターなど) を参照してください (Windows でのTeams Roomsのみ)

Teams Roomsデバイスを管理するには、[Microsoft Teams 管理センター](https://admin.teams.microsoft.com)を開き **、Windows** または **Surface Hubs** の **Teams デバイス** > Teams Roomsに移動します。

:::image type="content" source="../media/teams-rooms-summary2.png" alt-text="Teams 管理センターの [概要] ページをTeams Roomsします。":::


> [!IMPORTANT]
> Teams 管理センターを使用してデバイスを管理するには、グローバル管理者、Teams 管理者、または Teams デバイス管理者ロールを割り当てる必要があります。

## <a name="make-changes-to-teams-rooms-devices-or-surface-hubs"></a>Teams Rooms デバイスまたは Surface Hubs に変更を加える

複数のTeams Roomsまたは Surface Hub デバイスがある場合は、複数のデバイスで同時にほとんどのアクションを実行できます。 たとえば、すべてのTeams Roomsで Teams アプリの設定を同時に設定できます。

### <a name="device-settings"></a>デバイス設定

組織内の 1 つ以上のTeams Roomsまたは Surface Hubs の設定を変更できます。 設定を変更するには、管理するデバイスを選択し、**[設定の編集]** を選択します。 新しいウィンドウが開き、変更できるすべての設定が表示されます。 次の表に、Teams 管理センターを使用して変更できる設定を示します。 一部の設定は、1 つのTeams Roomsを選択した場合にのみ使用できます。

複数を選択した場合、一括編集をサポートする設定には、次の 2 つのオプションが表示されます。

- **既存の値を保持する** このオプションを選択した場合、選択したTeams Roomsの設定は変更されません。
- **既存の値を に置き換える** このオプションを選択した場合は、選択したTeams Roomsの設定を指定した値で更新できます。
    > [!CAUTION]
    > 更新を選択した設定の既存の値は、指定した値に置き換えられます。 既存の値のリストに追加する場合は、追加する値に既存の値を含める必要があります。 たとえば、設定に`contoso.com, fabrikam.com`の既存のドメインリストがあり、`northwindtraders.com`を追加する場合、指定する必要がある値は`contoso.com, fabrikam.com, northwindtraders.com`になります。
    >
    > 複数のTeams Roomsを選択すると、選択したすべてのデバイスの設定が指定した値に変更されます。 Teams Rooms設定の値が異なる場合は、すべて同じ値に更新されます。

| Setting                                                      | 指定できる値                                        | 一括編集をサポートする | サポートされているデバイスの種類 |
|--------------------------------------------------------------|--------------------------------------------------------|--------------------|------------------------|
| *Account*                                                    |                                                        |                    | Windows でのTeams Rooms |
| **電子メール**                                                    | メール アドレス                                          | いいえ                 | Windows でのTeams Rooms |
| **サポートされているミーティングモード**                                   | Microsoft Teams のみ<br>Skype for Business (既定) および Microsoft Teams<br>Skype for Business および Microsoft Teams (既定)<br>Skype for Business のみ|はい| Windows でのTeams Rooms |
| **先進認証**                                    | オン<br>オフ                                              | はい                | Windows でのTeams Rooms |
| **Exchange アドレス**                                         | メール アドレス                                          | いいえ                 | Windows でのTeams Rooms |
| **ドメイン\ユーザー名（オプション）**                               | アカウントのドメインとユーザー名                           | いいえ                 | Windows でのTeams Rooms |
| **ドメインを構成する**                                         | カンマ区切りリスト                                   | はい                | Windows でのTeams Rooms |
| *会議*                                                   |                                                        |                    | Windows、Surface Hubs でのTeams Rooms |
| **自動画面共有**                                 | オン<br>オフ                                              | はい                | Windows でのTeams Rooms |
| **HDMI 取り込みオーディオ共有**                                 | オン<br>オフ                                              | はい                | Windows でのTeams Rooms |
| **ミーティング名を表示**                                       | オン<br>オフ                                              | はい                | Windows でのTeams Rooms |
| **他の全員がミーティングを退出した場合は自動的に退出する**                 | オン<br>オフ                                              | はい                | Windows でのTeams Rooms |
| **サード パーティの会議に参加する**                 | Cisco Webex<br>ズーム                                              | Yes                | Windows、Surface Hubs でのTeams Rooms |
| **会議室情報と結合する**                 | 選択済み<br>選択されていません                                              | はい                | Windows、Surface Hubs でのTeams Rooms |
| **カスタム情報で結合する**                 | 選択済み<br>選択されていません                                              | はい                | Windows でのTeams Rooms |
| **名前 (必須)**                 | 部屋またはスペースの名前                                              | Yes                | Windows でのTeams Rooms |
| **Email (必須)**                 | メール アドレス                                              | はい                | Windows でのTeams Rooms |
| *デバイス*                                                     |                                                        |                    | Windows でのTeams Rooms |
| **デュアル モニター モード**                                        | オン<br>オフ                                              | はい                | Windows でのTeams Rooms |
| **コンテンツの複製を許可する** | 選択済み<br>選択されていません                                 | はい                | Windows でのTeams Rooms |
| **Bluetooth ビーコン**                                      | オン<br>オフ                                              | はい                | Windows、Surface Hubs でのTeams Rooms |
| **近接しているミーティングへの招待を自動的に受け入れる** | 選択済み<br>選択されていません                                 | はい                | Windows、Surface Hubs でのTeams Rooms |
| **ログをフィードバックと一緒に送信する**                                  | オン<br>オフ                                              | はい                | Windows でのTeams Rooms |
| **ログとフィードバック用のメールアドレス**                      | メール アドレス                                          | はい                | Windows でのTeams Rooms |
| *会議の調整*                                                     |                                                        |                    | Windows でのTeams Rooms |
| **調整された会議** | オン<br>オフ                                 | いいえ                | Windows、Surface Hubs でのTeams Rooms |
| **このデバイスのマイクをオンにする** | オン<br>オフ                                 | いいえ                | Windows、Surface Hubs でのTeams Rooms |
| **会議に参加するときにユーザーを有効にする** | 選択済み<br>選択されていません                                 | いいえ                | Windows、Surface ハブでのTeams Rooms |
| **このデバイスのカメラをオンにする** | オン<br>オフ                                 | いいえ                | Windows、Surface Hubs でのTeams Rooms |
| **会議に参加するときにユーザーを有効にする** | 選択済み<br>選択されていません                                 | いいえ                | Windows、Surface Hubs でのTeams Rooms |
| **このデバイスのホワイトボードを有効にする** | オン<br>オフ                                 | いいえ                | Windows、Surface Hubs でのTeams Rooms |
| **信頼されたデバイス アカウント (コンマで区切る)** | デバイスの一覧                              | いいえ                | Windows、Surface Hubs でのTeams Rooms |
| *周辺機器*                                                |                                                        |                    | Windows でのTeams Rooms |
| **会議用マイク**                                  | 使用可能なマイクの一覧                          | いいえ                 | Windows でのTeams Rooms |
| **会議用スピーカー**                                     | 使用可能なスピーカーの一覧                             | いいえ                 | Windows でのTeams Rooms |
| **既定のボリューム**                                           | 0-100                                                  | いいえ                 | Windows でのTeams Rooms |
| **既定のスピーカー**                                          | 使用可能なスピーカーの一覧                             | いいえ                 | Windows でのTeams Rooms |
| **既定のボリューム**                                           | 0-100                                                  | いいえ                 | Windows でのTeams Rooms |
| **コンテンツ カメラ**                                           | 使用できるカメラの一覧                              | いいえ                 | Windows でのTeams Rooms |
| **コンテンツカメラの拡張機能**                              | オン<br>オフ                                              | いいえ                 | Windows でのTeams Rooms |
| **コンテンツ カメラを180度回転**                        | オン<br>オフ                                              | いいえ                 | Windows でのTeams Rooms |
| *テーマ*                                                    |                                                        |                    | Windows でのTeams Rooms |
|                                                              | 既定値<br>テーマなし<br>カスタム<br>組み込みテーマの一覧   | はい                | Windows でのTeams Rooms |

[Surface Hubs を構成するためのその他のオプションについては、「Surface Hubs での Microsoft Teams](surface-hub-manage-config.md) 構成の管理」を参照してください。

### <a name="cortana-settings"></a>Cortana の設定

_Cortana for Voice Activation_ または Push を有効 _にして_、組織内のすべてのデバイスまたはデバイスごとに PowerShell を使用して話すことができます。

「Teams の Cortana 音声アシスタンス」の記事の「[Windows](../cortana-in-teams.md) でのMicrosoft Teams Rooms」を参照してください。

### <a name="front-row-layout-settings"></a>最前列レイアウト設定

フロント行は、Windows 上のTeams Roomsの会議ビュー レイアウト オプションです。

| Teams デバイス | アプリのバージョン | ルーム ディスプレイの前面 |
|--------------|-------------|-----------------------|
|Windows でのMicrosoft Teams Rooms | 4.11.12.0 以降 (最新バージョンをお勧めします) | 単一ディスプレイとデュアル ディスプレイをサポートします。最小サイズ: 46 インチ。縦横比 16:9 (1920x1080 解像度) または 21:9 (2560x1080 解像度)。Windows 設定では、すべてのディスプレイを 100% スケーリングで設定する必要があります |

フロント行の要件を満たすように表示設定を調整するには、「[Microsoft Teams Roomsメンテナンスと操作](rooms-operations.md#scale-and-resolution)」を参照してください。

フロント行を会議室の既定のレイアウトとして設定する方法、またはオフにする方法については、「[XML 構成ファイルを使用してMicrosoft Teams Roomsコンソール設定をリモートで管理する](xml-config-file.md#set-front-row-as-the-default-layout)」を参照してください。

フロント行の管理の詳細については、「 [既知の問題](known-issues.md#Limits) 」を参照してください。

## <a name="device-restart-options"></a>デバイス再起動のオプション

デバイス設定の変更は、デバイスが再起動された後にのみ有効になります。 再起動が必要な変更を行うときは、すぐに再起動するか、再起動をスケジュールするかを選択できます。 利用可能な再起動オプションは次のとおりです。

- **即時再起動** このオプションを選択した場合、変更するすべてのデバイスは、このオプションを選択するとすぐに再起動します。
- **スケジュールされた再起動** このオプションを選択すると、変更を加えるデバイスを、組織への影響が少ない時間帯に再起動できます。
  - **日時を選択** 特定の日付と時刻を選択して、デバイスを再起動します。 選択した日付と時刻は、再起動中のデバイスに対してローカルです。 
  - **毎晩の再起動時に更新プログラムを実行する** デバイスは、メンテナンスを実行するために毎晩再起動されます。 この再起動中に、デバイスに加えた変更が適用されます。

> [!CAUTION]
> 再起動時に使用されているTeams Roomsと Surface Hub は、再起動プロセスの間使用できなくなります。 進行中の会議から切断され、デバイスの再起動中に新しい会議に参加できなくなります。

## <a name="remove-device"></a>デバイスの削除

デバイスを削除すると、デバイスは組織から削除され、Teams 管理センターの Windows または Surface Hubs のTeams Roomsの一覧に表示されなくなります。

デバイスを削除しても有効なユーザー名とパスワードで構成されている場合は、Microsoft 365 に再度接続すると、Teams Roomsまたは Surface Hubs の一覧に自動的に再追加されます。

1つまたは複数のデバイスを削除するには、次の操作を行います。

1. Windows または **Surface Hubs** の **Teams デバイス** > **Teams Roomsに** 移動し、削除するデバイスを選択します。
2. **削除** を選択します。

## <a name="download-device-logs"></a>デバイスログをダウンロードする

Microsoft サポートから要求された場合、デバイスの診断ログファイルのコピーをダウンロードできます。 ログファイルは、Teams 管理センターからダウンロードできるように zip ファイルに圧縮されます。

Teams ミーティング デバイスからコンピューターにログをダウンロードするには、次の手順を実行します。

1. Windows または **Surface Hubs** の **Teams デバイス** > **Teams Roomsに** 移動し、ログをダウンロードするデバイスの名前を選択します。
1. **デバイスログのダウンロード** を選択します。 デバイスログが使用可能になるまでに数分かかることがあります。
1. **[履歴]** タブを選択し、**Diagnostics ファイル** で [ログファイルのリンク] を選択します。 デバイスの診断ログファイルを含むzipファイルが、ブラウザの既定のダウンロードフォルダにダウンロードされます。

## <a name="view-device-information"></a>デバイス情報を見る

Teams 管理センターから、組織内のすべてのデバイスの全体的な状態を表示し、各デバイスの詳細を個別に表示できます。

### <a name="teams-rooms-system-dashboard"></a>Teams ミーティング システムダッシュボード

Teams ミーティング システムダッシュボードでは、すべてのデバイスの状態と正常性が一目でわかるように表示されます。

### <a name="device-details-view"></a>デバイスの詳細の表示

デバイスの詳細情報を表示するには、デバイスリストからその名前を選択します。 詳細ビューでは、デバイスに関する次の情報を確認できます。

- **正常性状態** Teams Roomsまたは Surface Hub デバイスの全体的な正常性を示します。 正常性状態は、[ **正常]**、[ **緊急でない**]、[ **重大**]、または **[オフライン]** のいずれかです。
- **[以降オフライン]** は、Microsoft 365がデバイスと通信できた最後の時刻を表示します。
- **使用状況の状態** デバイスの現在の状態 ( **アイドル**、 **ビジー**、または **使用不可**) を表示します。 Windows 上のTeams Roomsに対してのみ。
- **周辺 機器** Teams Rooms デバイスに接続されている周辺機器とその正常性状態を表示します。 正常性状態には、 **接続済み** または **未接続** のいずれかが表示されます。 Windows 上のTeams Roomsに対してのみ。
- **健康** Teams Rooms デバイスに接続されている周辺機器、ネットワーク接続、必要なサービスへのサインイン状態、およびソフトウェア バージョン情報に関する詳細情報を表示します。
- **詳細** 製造元情報、ネットワーク IP アドレス、デバイスのシリアル/MAC アドレスTeams Rooms表示します。
- **[アクティビティ]** には、ミーティングの日時、参加者数、期間、音声品質など、過去のミーティングの詳細が表示されます。 ミーティングの詳細については、この記事の後半の[[ミーティングの活動の詳細]](#meeting-activity-details)セクションを参照してください。
- **歴史** 構成の更新、デバイスの再起動、デバイス ログのダウンロード リンクなど、Teams Roomsまたは Surface Hub デバイスでの管理アクティビティの履歴を表示します。

#### <a name="meeting-activity-details"></a>ミーティングアクティビティの詳細

デバイスの詳細の [ **アクティビティ** ] タブには、デバイスが時間の経過と同時に参加したすべての会議に関する概要と詳細情報が表示されます。 **[アクティビティ]** タブで、ミーティングがいつ開催されたか、ミーティングに参加している参加者の数、およびミーティング中のオーディオ品質を確認できます。

:::image type="content" source="../media/teams-rooms-meeting-activity-summary.png" alt-text="デバイス アクティビティの概要一覧をTeams Roomsします。":::

特定のミーティングに関する詳細情報を表示するには、ミーティングの日付と時刻を選択します。 ミーティングに参加できるのが2人のみの場合は、[参加者の詳細] ページが表示されます。表示されない場合は、参加者の概要ページが表示されます。

##### <a name="participant-summary"></a>参加者の概要

参加者の概要ページには、ミーティングに参加したすべての参加者が表示されます。 各参加者がミーティングに参加した時期、名前、音声品質、およびセッション中に使用された機能を確認できます。 参加者のセッションの詳細を表示するには、参加者のセッションの開始時刻を選択します。

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-summary.png" alt-text="デバイス会議の詳細をTeams Roomsします。":::

##### <a name="participant-details"></a>参加者の詳細

参加者の詳細ページには、参加者のセッションのエンドツーエンドの診断情報が表示されます。 次の図に示すように、**デバイス**、**システム**、および **接続** の情報が参加者とチームルームのデバイスに提供されます。 参加者と Teams ミーティングのデバイス間 **ネットワーク** 診断情報も表示されます。 詳細情報が必要なコンテキストのアイコンを選択します。 追加の診断情報については、**[詳細]** タブを選択してください。

:::image type="content" source="../media/teams-rooms-meeting-activity-participant-details.png" alt-text="デバイス呼び出しの詳細をTeams Roomsします。":::
