---
title: Microsoft Teams でのデバイスの管理
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: kelsawi
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.managedevices.overview
- ms.teamsadmincenter.devicemanagement.overview
description: 組織内の Teams で使用されているデバイスを管理する方法について説明します。
localization_priority: Normal
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 366a24706a80f6fe96cc8a3733022cc64f78ba7e
ms.sourcegitcommit: 3ed779277540589eabef745685ab6c67d8a8ff90
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/19/2020
ms.locfileid: "44281723"
---
# <a name="manage-your-devices-in-microsoft-teams"></a>Microsoft Teams でのデバイスの管理

管理者は、Microsoft Teams 管理センターで、組織内の Teams で使用されているデバイスを管理することができます。 組織のデバイスのインベントリを表示して管理できます。また、デバイスの診断の更新、再起動、監視などのタスクを実行することができます。 構成プロファイルを作成して、1つのデバイスまたはデバイスのグループに割り当てることもできます。 

## <a name="what-devices-can-you-manage"></a>どのデバイスを管理できますか?
Teams で認定され、登録されているすべてのデバイスを管理することができます。 デバイスは、ユーザーが初めてデバイス上の Teams にサインインしたときに自動的に登録されます。 管理可能なデバイスの一覧については、以下を参照してください。

- [電話会議](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=16)
- [卓上電話](https://products.office.com/microsoft-teams/across-devices/devices/category?devicetype=34)
- コラボレーションバー

デバイスは、 [Microsoft Teams 管理センター](https://admin.teams.microsoft.com)の左側のナビゲーションにある [**デバイス**] に管理されます。

> [!NOTE]
> Microsoft Intune を使用している場合、デバイスは自動的に Intune に登録されます。 デバイスが登録されると、デバイスのコンプライアンスが確認され、条件付きアクセスポリシーがデバイスに適用されます。

## <a name="manage-phones-and-collaboration-bars-in-teams"></a>Teams で電話とコラボレーションバーを管理する

電話とコラボレーションバーは、Microsoft Teams 管理センターでも同じように管理されますが、[**デバイス**] の左側のナビゲーションにはそれぞれのセクションがあります。 これにより、各種類のデバイスを個別に管理することができます。

ここでは、組織のチームに登録されている携帯電話とコラボレーションバーを表示して管理することができます。 各デバイスに表示される情報には、デバイス名、製造元、モデル、ユーザー、状態、操作、最後の表示、履歴が含まれます。 目的に合った情報が表示されるように、ビューをカスタマイズすることができます。

組織のチームデバイスを管理する方法の例を次に示します。  
    
|操作方法  |操作 |
|---------|---------|
|デバイスの情報を変更する   | [**編集**] > デバイスを選択します。 デバイス名、アセットタグ、メモの追加などの詳細を編集できます。     |
|ソフトウェアの更新を管理する   |**更新**> デバイスを選択します。 デバイスで利用可能なソフトウェアとファームウェアの更新プログラムの一覧を表示し、インストールする更新プログラムを選ぶことができます。    |
|デバイスを再起動する   |デバイスを選択し >**再起動**します。          |
|デバイス履歴の表示  | デバイス > の**履歴**を選択します。 デバイスの更新履歴を表示できます。     |
|診断の表示  | **診断**> デバイスを選択します。        |

## <a name="use-configuration-profiles-in-teams"></a>Teams で構成プロファイルを使用する

構成プロファイルを使用して、組織内のチームデバイスの設定と機能を管理します。 構成プロファイルを作成またはアップロードして、有効または無効にする設定や機能を含め、デバイスまたはデバイスのグループにプロファイルを割り当てることができます。 

### <a name="create-a-configuration-profile"></a>構成プロファイルを作成する

1. 左側のナビゲーションで、[**デバイス**  >  **構成プロファイル**] に移動します。
2. **[追加]** をクリックします。
3. プロファイルの名前を入力し、必要に応じてわかりやすい説明を追加します。
4. プロファイルに必要な設定を指定し、[**保存**] をクリックします。

### <a name="assign-a-configuration-profile"></a>構成プロファイルを割り当てる

1. 左側のナビゲーションで、[**デバイス**  >  **構成プロファイル**] に移動します。
2. 割り当てる**構成プロファイル**を選び、[**デバイスへの割り当て**] をクリックします。  
3. [**構成プロファイルへのデバイスの割り当て**] ウィンドウで、割り当てるデバイスを検索して選びます。
4. **[保存]** をクリックします。
