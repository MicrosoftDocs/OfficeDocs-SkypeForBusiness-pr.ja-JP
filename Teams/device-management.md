---
title: Microsoft Teams でのデバイスを管理する
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 11/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: kelsawi
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1keywords:
- ms.teamsadmincenter.devicemanagement.overview
- ms.teamsadmincenter.managedevices.overview
description: 組織内の Teams で使用されているデバイスを管理する方法について説明します。
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 76692714bbf58dca7bd74461bed4da34abf55c58
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/22/2019
ms.locfileid: "34344642"
---
# <a name="manage-your-devices-in-microsoft-teams"></a>Microsoft Teams でのデバイスを管理する

::: zone target="docs"
管理者は、Microsoft Teams & Skype for Business 管理センターで、組織内の Teams で使用されているすべてのデバイスを管理します。 組織のデバイスのインベントリを表示して管理できます。また、デバイスの診断の更新、再起動、監視などのタスクを実行することができます。 構成プロファイルを作成して、1つのデバイスまたはデバイスのグループに割り当てることもできます。 

## <a name="what-devices-can-you-manage"></a>どのデバイスを管理できますか?
チームに対して認定され、チームに登録されているデバイス。 デバイスは、ユーザーが初めてデバイス上の Teams にサインインしたときに自動的に登録されます。 管理可能なデバイスの一覧については、「[会議電話](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=16)と[卓上電話](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=34)」をご覧ください。

> [!NOTE]
> Microsoft Intune を使用している場合、デバイスは自動的に Intune に登録されます。 デバイスが登録されると、デバイスのコンプライアンスが確認され、条件付きアクセスポリシーがデバイスに適用されます。 

## <a name="manage-devices-in-teams"></a>Teams でデバイスを管理する

![Microsoft teams](media/teams-logo-30x30.png) **管理センターを使用し**た microsoft teams ロゴを示すアイコン

1. 左側のナビゲーションで、[**デバイス** > の**管理**] に移動します。
2. [**すべてのデバイス**] を選びます。  

::: zone-end

 ここでは、組織内の Teams に登録されているすべてのデバイスを表示および管理できます。 各デバイスに表示される情報には、デバイス名、製造元、モデル、ユーザー、状態、操作、最後の表示、履歴が含まれます。 目的に合った情報が表示されるように、ビューをカスタマイズすることができます。

 組織のチームデバイスを管理する方法の例を次に示します。  
    
|操作方法  |操作 |
|---------|---------|
|デバイスの情報を変更する   | デバイス >**編集**を選択します。 デバイス名、ユーザー情報、資産タグ、メモの追加などの詳細を編集できます。     |
|ソフトウェアの更新を管理する   |デバイス > の**更新プログラム**を選択します。 デバイスで利用可能なソフトウェアとファームウェアの更新プログラムの一覧を表示し、インストールする更新プログラムを選ぶことができます。    |
|デバイスを再起動する   |デバイス > を選択して**再起動**します。          |
|デバイス履歴の表示  | デバイスの >**履歴**を選択します。 デバイスの更新履歴を表示できます。     |
|診断の表示  | デバイス >**診断**を選択します。        |

## <a name="use-configuration-profiles-in-teams"></a>Teams で構成プロファイルを使用する

構成プロファイルを使用して、組織内のチームデバイスの設定と機能を管理します。 構成プロファイルを作成またはアップロードして、有効または無効にする設定や機能を含め、デバイスまたはデバイスのグループにプロファイルを割り当てることができます。 

### <a name="create-a-configuration-profile"></a>構成プロファイルを作成する

::: zone target="docs"

![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) Microsoft Teams & Skype for Business 管理センターを使用する

1. 左側のナビゲーションで、[**デバイス** > の**管理**] に移動します。

::: zone-end

2. [**構成プロファイル**] を選択し、[**新しい構成プロファイル**] を選択します。
3. プロファイルの名前を入力し、必要に応じてわかりやすい説明を追加します。
4. プロファイルに必要な設定を指定し、[**保存**] をクリックします。

### <a name="assign-a-configuration-profile"></a>構成プロファイルを割り当てる

::: zone target="docs"

![Microsoft Teams ロゴを示すアイコン](media/teams-logo-30x30.png) Microsoft Teams & Skype for Business 管理センターを使用する

1. 左側のナビゲーションで、[**デバイス** > の**管理**] に移動します。

::: zone-end

2. [**構成プロファイル**] を選び、割り当てるプロファイルの [**担当**者] でリンクをクリックします。  
3. [**構成プロファイルへのデバイスの割り当て**] ウィンドウで、割り当てるデバイスを検索して選びます。
4. [**保存**] をクリックします。
