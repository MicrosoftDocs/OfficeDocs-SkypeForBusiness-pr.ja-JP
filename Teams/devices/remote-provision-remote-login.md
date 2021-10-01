---
title: Android デバイスのリモート プロビジョニングTeamsサインイン
author: serdarsoysal
ms.author: serdars
manager: serdars
ms.reviewer: prgholve
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
description: Android デバイスのリモート プロビジョニングとサインインを行うTeams説明します
ms.openlocfilehash: 818a6a4fc7941c82a52d63016bbdc338f977be29
ms.sourcegitcommit: cfc48dc03550c093c4405fb5984648188f523699
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/01/2021
ms.locfileid: "60046153"
---
# <a name="remote-provisioning-and-sign-in-for-teams-android-devices"></a>Android デバイスのリモート プロビジョニングTeamsサインイン

IT 管理者は、Android デバイスを使用してリモートでプロビジョニングTeamsサインインできます。 デバイスをリモートでプロビジョニングするには、管理者がプロビジョニングするデバイスの MAC の ID をアップロードし、確認コードを作成する必要があります。 プロセス全体は、管理センターからリモートTeams完了できます。

## <a name="review-the-supported-devices"></a>サポートされているデバイスを確認する

次の一覧は、Android デバイスファームウェアの要件を示しています。

|デバイス カテゴリ|デバイス モデル|ファームウェアのバージョン|
|-|-|-|
|Teams電話|Yealink T55/T56/T58|58.15.0.124|
|Teams電話|Yealink VP59|91.15.0.58|
|Teams電話|Yealink CP960|73.15.0.117|
|Teams電話|Yealink MP56/MP54/MP58|122.15.0.36|
|Teams電話|クレスロン UC-2|1.0.3.52|
|Teams電話|  Poly Trio C60|  7.0.2.1071|
|Teams電話|  CCX400/CCX500/CCX600    |7.0.2.1072|
|Teams電話|  オーディオ コード C448HD/C450HD/C470HD|   1.10.120|
|Teams パネル|  クレスロン 770/1070|  1.004.0115|
|TeamsAndroid の会議室|Logitech Rally Bar Mini|1.2.982|
|TeamsAndroid の会議室|Logitech Rally Bar|1.2.982|
|TeamsAndroid の会議室|AudioCodes RXV80|1.13.361|
|TeamsAndroid の会議室|EPOS EXPAND Vision 3T|1.2.2.21182.10|
|TeamsAndroid の会議室|Yealink MeetingBar A30|133.15.0.60|
|TeamsAndroid の会議室|Yealink MeetingBar A20|133.15.0.60|
|TeamsAndroid の会議室|Yealink CTP18 タッチ コンソール|137.15.0.37|
|TeamsAndroid の会議室|Poly Studio X30|3.5.0.344025|
|TeamsAndroid の会議室|Poly Studio X50|3.5.0.344025|
|TeamsAndroid の会議室|Poly TC8 タッチ コンソール |3.5.0.210489|
|TeamsAndroid の会議室|Yealink VC210|118.15.0.54|

## <a name="add-a-device-mac-address"></a>デバイスの MAC アドレスを追加する

新しいデバイスをプロビジョニングするには、次の手順を実行します。

1. Teams 管理センターにサインインします。
2. [デバイスTeams 展開 **します**。
3. [アクション **] タブから [新しい** デバイスのプロビジョニング **] を** 選択します。

[新 **しいデバイスのプロビジョニング]** ウィンドウで、MAC アドレスを手動で追加するか、ファイルをアップロードできます。

### <a name="manually-add-a-device-mac-address"></a>デバイスの MAC アドレスを手動で追加する

1. [アクティブ化 **待ち] タブで****、[MAC ID の追加] を選択します**。

   ![デバイスの Mac アドレスを手動で追加します。](../media/remote-provision-6-new.png)

1. MAC ID を入力します。
1. 場所を入力します。これは、技術者がデバイスをインストールする場所を特定するのに役立ちます。
1. 完了したら **、[適用** ] を選択します。

### <a name="upload-a-file-to-add-a-device-mac-address"></a>アップロード MAC アドレスを追加するファイルを作成する

1. [アクティブ **化待ち]** タブで、[MAC **アップロード を選択します**。
2. ファイル テンプレートをダウンロードします。
3. MAC ID と場所を入力し、ファイルを保存します。
4. **ファイル を選択** し、[ファイル]**をアップロード。**

## <a name="generate-a-verification-code"></a>確認コードを生成する

デバイスの確認コードが必要です。 確認コードは、一括またはデバイス レベルで生成され、24 時間有効です。

1. [アクティブ **化待ち] タブ** で、既存の MAC ID を選択します。
   MAC アドレスのパスワードが作成され、[確認コード] 列 **に表示** されます。

2. MAC の一覧と確認コードを現場の技術者に提供します。 ファイル内の詳細を直接エクスポートし、実際のインストール作業を行っている技術者とファイルを共有できます。

## <a name="provision-the-device"></a>デバイスをプロビジョニングする

デバイスの電源が入り、ネットワークに接続されると、技術者がデバイスをプロビジョニングします。 これらの手順は、デバイス上でTeamsされます。

1. 技術者が[デバイスの **プロビジョニング] を****選択設定。**  

   ![[アクション] タブから新しいデバイス オプションをプロビジョニングします。](../media/provision-device1.png)
  
2. 技術者は、指定された入力フィールドにデバイス固有の確認コードを入力します。

   ![新しいデバイス検証をプロビジョニングします。](../media/provision-device-verification1.png)

   デバイスが正常にプロビジョニングされると、テナント名がサインイン ページに表示されます。

   ![サインイン ページのテナント名。](../media/provision-code.png)

## <a name="sign-in-remotely"></a>リモートでサインインする

プロビジョニングされたデバイスが [サインインの待機中 **] タブに表示** されます。個々のデバイスを選択して、リモート サインイン プロセスを開始します。

1. [サインイン待ち] **タブからデバイスを選択** します。

   ![サインインできるデバイスの一覧が表示されたウィンドウ。](../media/remote-device1.png)

2. 「ユーザーにサインインする」 **の指示に従って、[** 閉じる] を **選択します**。

   ![個々のデバイスの [ユーザーのサインイン] ウィンドウ。](../media/sign-in-user.png)

## <a name="related-article"></a>関連記事

- [Teams でのデバイスの管理](device-management.md)
- [デバイスTeamsをリモートで更新する](remote-update.md)
