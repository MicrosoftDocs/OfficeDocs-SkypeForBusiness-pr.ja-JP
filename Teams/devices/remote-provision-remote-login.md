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
ms.openlocfilehash: f39b93a048cee84cf6890d063e272edbef5edb4e
ms.sourcegitcommit: 1ee9b1857f472a5b95352f7471c0cf21be6ea0c3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2021
ms.locfileid: "52059191"
---
# <a name="remote-provisioning-and-sign-in-for-teams-android-devices"></a>Teams Android デバイスのリモート プロビジョニングとサインイン

IT 管理者は、Teams Android デバイスをリモートでプロビジョニングしてサインインできます。 デバイスをリモートでプロビジョニングするには、管理者がプロビジョニングされているデバイスの MAC の ID をアップロードし、確認コードを作成する必要があります。 Teams 管理センターからリモートでプロセス全体を完了できます。

## <a name="review-the-supported-devices"></a>サポートされているデバイスを確認する

次の一覧は、Android デバイスのファームウェア要件を示しています。

|デバイス のカテゴリ|デバイス モデル|ファームウェアのバージョン|
|-|-|-|
|Teams の電話|Yealink T55/T56/T58|58.15.0.124|
|Teams の電話|Yealink VP59|91.15.0.58|
|Teams の電話|Yealink CP960|73.15.0.117|
|Teams の電話|Yealink MP56/MP54/MP58|122.15.0.36|
|Teams の電話|クレストロン UC-2|1.0.3.52|
|Teams の電話|  Poly Trio C60|  7.0.2.1071|
|Teams の電話|  CCX400/CCX500/CCX600    |7.0.2.1072|
|Teams の電話|  オーディオ コード C448HD/C450HD/C470HD|   1.10.120|

## <a name="add-a-device-mac-address"></a>デバイスの MAC アドレスを追加する

新しいデバイスをプロビジョニングするには、次の手順を実行します。

1. Teams 管理センターにサインインします。
2. [デバイス] **を展開します**。
3. [アクション **] タブの [新しい** デバイスのプロビジョニング **] を** 選択します。

[新 **しいデバイスのプロビジョニング]** ウィンドウで、MAC アドレスを手動で追加するか、ファイルをアップロードできます。

### <a name="manually-add-a-device-mac-address"></a>デバイスの MAC アドレスを手動で追加する

1. [アクティブ化 **の待ち] タブで****、[MAC ID の追加] を選択します**。

   ![デバイスの Mac アドレスを手動で追加する](../media/remote-provision-6.png)

1. MAC ID を入力します。
1. 技術者がデバイスをインストールする場所を特定するのに役立つ場所を入力します。
1. 完了したら **、[適用** ] を選択します。

### <a name="upload-a-file-to-add-a-device-mac-address"></a>ファイルをアップロードしてデバイスの MAC アドレスを追加する

1. [アクティブ **化を待っている]** タブで **、[MAC のアップロードの CD] を選択します**。
2. ファイル テンプレートをダウンロードします。
3. MAC ID と場所を入力し、ファイルを保存します。
4. **[ファイル] を** 選択し、[アップロード] **を選択します**。

## <a name="generate-a-verification-code"></a>確認コードを生成する

デバイスの確認コードが必要です。 検証コードは、一括またはデバイス レベルで生成され、24 時間有効です。

1. [アクティブ **化の待ち]** タブで、既存の MAC ID を選択します。
   MAC アドレスのパスワードが作成され、[確認コード] 列 **に表示** されます。

2. MAC の一覧と確認コードをフィールド技術者に提供します。 ファイル内の詳細を直接エクスポートし、実際のインストール作業を行っている技術者とファイルを共有できます。

## <a name="provision-the-device"></a>デバイスをプロビジョニングする

デバイスの電源がオンでネットワークに接続されると、技術者はデバイスをプロビジョニングします。 これらの手順は、Teams デバイスで完了します。

1. 技術者が [設定] **から [デバイスのプロビジョニング]** を **選択します**。  

   ![[アクション] タブから新しいデバイス オプションをプロビジョニングする](../media/provision-device1.png)
  
2. 技術者は、指定された入力フィールドにデバイス固有の確認コードを入力します。

   ![新しいデバイスの検証をプロビジョニングする](../media/provision-device-verification1.png)

   デバイスが正常にプロビジョニングされると、サインイン ページにテナント名が表示されます。

   ![サインイン ページのテナント名](../media/provision-code.png)

## <a name="sign-in-remotely"></a>リモートでサインインする

プロビジョニングされたデバイスが [サインインの待ち] **タブに表示** されます。個々のデバイスを選択して、リモート サインイン プロセスを開始します。

1. [サインインを待っている] **タブからデバイスを選択** します。

   ![サインインの準備が整ったデバイスの一覧が表示されたウィンドウ。](../media/remote-device1.png)

2. [ユーザーのサインイン] の **指示に従って、[閉** じる] を **選択します**。

   ![個々のデバイスの [ユーザーのサインイン] ウィンドウ](../media/sign-in-user.png)

## <a name="related-article"></a>関連記事

- [Teams でのデバイスの管理](device-management.md)
- [Teams デバイスをリモートで更新する](remote-update.md)
