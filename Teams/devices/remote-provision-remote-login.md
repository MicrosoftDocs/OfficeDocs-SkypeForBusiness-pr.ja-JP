---
title: Teams Android デバイスのリモート プロビジョニングとサインイン
author: cazawideh
ms.author: czawideh
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Teams Android デバイスのリモート プロビジョニングとサインインの方法について説明します
ms.openlocfilehash: e7e5acd491f15d4cc52ce1b898112da868f80594
ms.sourcegitcommit: a3b3eb85354d62b2a5325ba7c8dda88352c6711a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/18/2021
ms.locfileid: "61070151"
---
# <a name="remote-provisioning-and-sign-in-for-teams-android-devices"></a>Teams Android デバイスのリモート プロビジョニングとサインイン

IT 管理者は、Teams Android デバイスをリモートでプロビジョニングしてサインインできます。 デバイスをリモートでプロビジョニングするには、管理者がプロビジョニングするデバイスの MAC ID をアップロードし、検証コードを作成する必要があります。 プロセス全体は、Teams管理センターからリモートで完了できます。

## <a name="review-the-supported-devices"></a>サポートされているデバイスを確認する

次の一覧は、Android デバイスのファームウェア要件を示しています。

|デバイス カテゴリ|デバイス モデル|ファームウェアのバージョン|
|-|-|-|
|Teams電話|Yealink T55/T56/T58|58.15.0.124|
|Teams電話|Yealink VP59|91.15.0.58|
|Teams電話|Yealink CP960|73.15.0.117|
|Teams電話|Yealink MP56/MP54/MP58|122.15.0.36|
|Teams電話|レストロン UC-2|1.0.3.52|
|Teams電話|  PolyTrio C60|  7.0.2.1071|
|Teams電話|  CCX400/CCX500/CCX600    |7.0.2.1072|
|Teams電話|  オーディオ コード C448HD/C450HD/C470HD|   1.10.120|
|Teams パネル|  770/1070|  1.004.0115|
|Android でのTeams Rooms|Logitech Rally Bar Mini|1.2.982|
|Android でのTeams Rooms|Logitech Rally Bar|1.2.982|
|Android でのTeams Rooms|AudioCodes RXV80|1.13.361|
|Android でのTeams Rooms|エポポス EXPAND Vision 3T|1.2.2.21182.10|
|Android でのTeams Rooms|Yealink MeetingBar A30|133.15.0.60|
|Android でのTeams Rooms|Yealink MeetingBar A20|133.15.0.60|
|Android でのTeams Rooms|Yealink CTP18 タッチ コンソール|137.15.0.37|
|Android でのTeams Rooms|Poly Studio X30|3.5.0.344025|
|Android でのTeams Rooms|Poly Studio X50|3.5.0.344025|
|Android でのTeams Rooms|Poly TC8 タッチ コンソール |3.5.0.210489|
|Android でのTeams Rooms|Yealink VC210|118.15.0.54|

## <a name="add-a-device-mac-address"></a>デバイスの MAC アドレスを追加する

新しいデバイスをプロビジョニングするには、次の手順を実行します。

1. Teams 管理センターにサインインします。
2. **[Teams デバイス] を展開します**。
3. [アクション] タブで [**新しいデバイスのプロビジョニング****] を** 選択します。

[ **新しいデバイスのプロビジョニング** ] ウィンドウで、MAC アドレスを手動で追加するか、ファイルをアップロードできます。

### <a name="manually-add-a-device-mac-address"></a>デバイスの MAC アドレスを手動で追加する

1. [ **アクティブ化の待機中** ] タブで、[ **MAC ID の追加**] を選択します。

   ![デバイスの mac アドレスを手動で追加します。](../media/remote-provision-6-new.png)

1. MAC ID を入力します。
1. 場所を入力します。これは、技術者がデバイスをインストールする場所を特定するのに役立ちます。
1. [ **完了時に適用]** を選択します。

### <a name="upload-a-file-to-add-a-device-mac-address"></a>デバイスの MAC アドレスを追加するファイルをアップロードする

1. [**アクティブ化の待機中**] タブで、**MAC ID アップロード** 選択します。
2. ファイル テンプレートをダウンロードします。
3. MAC ID と場所を入力し、ファイルを保存します。
4. **ファイルを選択** し、**アップロード** を選択します。

## <a name="generate-a-verification-code"></a>確認コードを生成する

デバイスの確認コードが必要です。 検証コードは、一括またはデバイス レベルで生成され、24 時間有効です。

1. [ **アクティブ化の待機中** ] タブで、既存の MAC ID を選択します。
   MAC アドレスのパスワードが作成され、[ **確認コード** ] 列に表示されます。

2. MAC ID と検証コードの一覧をフィールド技術者に提供します。 詳細をファイルに直接エクスポートし、実際のインストール作業を行っている技術者とファイルを共有できます。

## <a name="provision-the-device"></a>デバイスをプロビジョニングする

デバイスの電源がオンになり、ネットワークに接続されると、技術者はデバイスをプロビジョニングします。 これらの手順は、Teams デバイスで完了します。

1. 技術者は **、設定** から **[デバイスのプロビジョニング**] を選択します。  

   ![[アクション] タブから新しいデバイス オプションをプロビジョニングします。](../media/provision-device1.png)
  
2. 技術者は、指定された入力フィールドにデバイス固有の検証コードを入力します。

   ![新しいデバイス検証をプロビジョニングします。](../media/provision-device-verification1.png)

   デバイスが正常にプロビジョニングされると、サインイン ページにテナント名が表示されます。

   ![サインイン ページのテナント名。](../media/provision-code.png)

## <a name="first-time-remote-sign-in"></a>初めてのリモート サインイン

プロビジョニングされたデバイスが [ **サインイン待ち** ] タブに表示されます。個々のデバイスを選択して、リモート サインイン プロセスを開始します。

1. [ **サインイン待ち** ] タブからデバイスを選択します。

   ![サインインの準備が整ったデバイスの一覧が表示されたウィンドウ。](../media/remote-device1.png)

2. ユーザーのサインインの指示 **に** 従って、[ **閉じる**] を選択します。

   ![個々のデバイスの [ユーザーのサインイン] ウィンドウ。](../media/sign-in-user.png)

## <a name="related-articles"></a>関連記事

- [Teams でのデバイスの管理](device-management.md)
- [リモート サインインとサインアウト](remote-sign-in-and-sign-out.md)
- [Teams デバイスをリモートで更新する](remote-update.md)
