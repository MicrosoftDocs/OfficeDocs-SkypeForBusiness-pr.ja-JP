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
description: 組織のチームと共同で使用するデバイスを管理する方法について説明します。
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 20798daf34c4759b91c4926b209847aa51ddd668
ms.sourcegitcommit: 70d4d02a3cc894f2f197aeea459ac079cde63877
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/11/2019
ms.locfileid: "30541649"
---
# <a name="manage-your-devices-in-microsoft-teams"></a>Microsoft Teams でのデバイスを管理する

::: zone target="docs"
管理者としては、チームを使用、マイクロソフトのチーム & Skype から、組織のビジネス管理センターのすべてのデバイスを管理します。 表示し、組織のデバイスのインベントリを管理し、更新、再起動、デバイスのモニター診断などのタスクを実行できます。 作成し、デバイスまたはデバイスのグループに構成プロファイルを割り当てることができます。 

## <a name="what-devices-can-you-manage"></a>どのようなデバイスを管理することができますか。
デバイスは、チームの認定し、チームに登録する必要があります。 デバイスでは、初めてのユーザーが署名チームに、デバイス上に自動的に登録が。 管理可能な認定済みのデバイスのリストは、[会議電話](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=16)と[デスクの電話](https://products.office.com/en-us/microsoft-teams/across-devices/devices/category?devicetype=34)を参照してください。

> [!NOTE]
> Microsoft Intune があれば、デバイスは自動的に Intune に登録します。 デバイスを登録すると後、デバイスのコンプライアンスを確認し、条件付きのアクセス ポリシーは、デバイスに適用します。 

## <a name="manage-devices-in-teams"></a>チーム内のデバイスを管理します。

![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) **、マイクロソフトのチーム管理センターを使用して**

1. 左側のナビゲーションでは、**デバイス**に移動 > **デバイスの管理**です。
2. **すべてのデバイス**を選択します。  

::: zone-end

 ここでは、表示し、組織内のチームに登録されているすべてのデバイスを管理できます。 デバイスごとに表示される情報には、デバイス名、製造元、モデル、ユーザー、状態、アクション、最後の表示、および履歴が含まれています。 お客様のニーズに合った情報を表示するビューをカスタマイズすることができます。

 組織内のチームのデバイスを管理する方法のいくつかの例を次に示します。  
    
|これを行う.  |この操作を行う |
|---------|---------|
|デバイスの情報を変更します。   | デバイス _gt が**編集**を選択します。 デバイス名、ユーザー情報、資産タグなどの詳細を編集し、メモを追加できます。     |
|ソフトウェア更新プログラムを管理します。   |デバイス _gt**更新プログラム**を選択します。 デバイスで利用できるソフトウェアおよびファームウェアの更新の一覧を表示し、インストールする更新プログラムを選択できます。    |
|デバイスを再起動します。   |デバイス _gt が**再起動**を選択します。          |
|デバイスの履歴を表示します  | デバイス _gt**履歴**を選択します。 デバイスの更新履歴を表示することができます。     |
|診断を表示します。  | デバイス _gt**診断プログラム**を選択します。        |

## <a name="use-configuration-profiles-in-teams"></a>構成プロファイルを使用して、チームで

構成プロファイルを使用すると、組織内のチームのデバイスの設定および機能を管理できます。 作成したり、設定、およびデバイスまたはデバイスのグループにプロファイルを割り当てるを有効または無効にする機能など、構成プロファイルをアップロードすることができます。 

### <a name="create-a-configuration-profile"></a>構成プロファイルを作成します。

::: zone target="docs"

![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) マイクロソフト チーム & Skype を使用するビジネス管理センターの

1. 左側のナビゲーションでは、**デバイス**に移動 > **デバイスの管理**です。

::: zone-end

2. **構成プロファイル**を選択し、**新しい構成プロファイル**を選択します。
3. プロファイルの名前を入力し、わかりやすい説明を追加する場合は、します。
4. プロファイルに使用設定を指定し、[**保存**] をクリックします。

### <a name="assign-a-configuration-profile"></a>構成プロファイルを割り当てる

::: zone target="docs"

![チーム ・ ロゴ ・ 30x30.png](media/teams-logo-30x30.png) マイクロソフト チーム & Skype を使用するビジネス管理センターの

1. 左側のナビゲーションでは、**デバイス**に移動 > **デバイスの管理**です。

::: zone-end

2. **構成プロファイル**を選択し、割り当てるプロファイルの**割り当て先**] の下のリンクをクリックします。  
3. **構成プロファイルにデバイスを割り当てる**ペインで、検索し、割り当てるデバイスを選択します。
4. [**保存**] をクリックします。
