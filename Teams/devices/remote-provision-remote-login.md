---
title: Teams Android デバイスのリモート プロビジョニングとサインイン
author: cichur
ms.author: v-cichur
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
localization_priority: Normal
search.appverid: MET150
description: Teams Android デバイスのリモート プロビジョニングとサインインの方法について説明します。
ms.openlocfilehash: 43a025c0cc68fb7f10015d69298f8dd75f9003e8
ms.sourcegitcommit: 95386369e2256ba382b4d6e34adb7473de050b26
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/29/2021
ms.locfileid: "51410357"
---
# <a name="remote-provisioning-and-sign-in-for-teams-android-devices"></a>Teams Android デバイスのリモート プロビジョニングとサインイン

IT 管理者は、リモートで Teams Android デバイスをプロビジョニングしてサインインできます。 リモートでデバイスをプロビジョニングするには、管理者がプロビジョニングされているデバイスの MAC ID をアップロードし、確認コードを作成する必要があります。 Teams 管理センターからリモートでプロセス全体を完了できます。

## <a name="review-the-supported-devices"></a>サポートされているデバイスを確認する

次の一覧は、Android デバイスのファームウェア要件を示しています。

|デバイス カテゴリ|デバイス モデル|ファームウェアのバージョン|
|-|-|-|
|Teams の電話|Yealink T55/T56/T58|58.15.0.124|
|Teams の電話|Yealink VP59|91.15.0.58|
|Teams の電話|Yealink CP960|73.15.0.117|
|Teams の電話|Yealink MP56/MP54/MP58|122.15.0.36|
|Teams の電話|クレットロン UC-2|1.0.3.52|

## <a name="add-a-device-mac-address"></a>デバイスの MAC アドレスを追加する

新しいデバイスをプロビジョニングするには、次の手順を実行します。

1. Teams 管理センターにサインインします。
2. [デバイス **] を展開します**。
3. [操作 **] タブから [新しい** デバイスのプロビジョニング **] を選択** します。

[新 **しいデバイスのプロビジョニング** ] ウィンドウで、MAC アドレスを手動で追加するか、ファイルをアップロードできます。

### <a name="manually-add-a-device-mac-address"></a>デバイスの MAC アドレスを手動で追加する

1. [ライセンス認証 **待ち] タブで****、[MAC ID の追加] を選択します**。

   ![デバイスの Mac アドレスを手動で追加する](../media/remote-provision-6.png)

1. MAC ID を入力します。
1. 場所を入力すると、技術者がデバイスをインストールする場所を特定できます。
1. 完了 **したら [適用** ] を選択します。

### <a name="upload-a-file-to-add-a-device-mac-address"></a>ファイルをアップロードしてデバイスの MAC アドレスを追加する

1. [ライセンス **認証待ち]** タブで **、[MAC のアップロード] を選び、**
2. ファイル テンプレートをダウンロードします。
3. MAC ID と場所を入力し、ファイルを保存します。
4. **ファイルを選択し**、[アップロード] を **選択します**。

## <a name="generate-a-verification-code"></a>確認コードを生成する

デバイスの確認コードが必要です。 確認コードは、一括またはデバイス レベルで生成され、24 時間有効です。

1. [ライセンス **認証待ち]** タブで、既存の MAC ID を選択します。
   MAC アドレスのパスワードが作成され、[確認コード] 列 **に表示** されます。

2. フィールド技術者に MAC の ID と確認コードの一覧を提供します。 ファイルに詳細を直接エクスポートし、実際のインストール作業を行っている技術者とファイルを共有できます。

## <a name="provision-the-device"></a>デバイスをプロビジョニングする

デバイスの電源が入り、ネットワークに接続されると、技術者がデバイスをプロビジョニングします。 これらの手順は、Teams デバイスで完了します。

1. 技術者が [設定] **から [プロビジョニング デバイス** ] を **選択します**。  

   ![[操作] タブから新しいデバイス オプションをプロビジョニングする](../media/provision-device1.png)
  
2. 技術者は、指定された入力フィールドにデバイス固有の確認コードを入力します。

   ![新しいデバイスの確認をプロビジョニングする](../media/provision-device-verification1.png)

   デバイスのプロビジョニングが正常に完了すると、テナント名がサインイン ページに表示されます。

   ![サインイン ページのテナント名](../media/provision-code.png)

## <a name="sign-in-remotely"></a>リモートでサインインする

プロビジョニングされたデバイスが [サインイン待ち **] タブに表示** されます。個々のデバイスを選択してリモート サインイン プロセスを開始します。

1. [サインイン待ち] タブ **からデバイスを選択** します。

   ![サインインできるデバイスの一覧が表示されたウィンドウ。](../media/remote-device1.png)

2. [サインイン] の指示 **に従ってユーザーをサインインし**、[閉じる] を **選択します**。

   ![個々のデバイスのユーザー ウィンドウにサインインする](../media/sign-in-user.png)

## <a name="related-article"></a>関連記事

- [Teams でのデバイスの管理](device-management.md)
- [Teams デバイスをリモートで更新する](remote-update.md)
