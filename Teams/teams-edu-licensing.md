---
title: 教育機関向けの Microsoft Teams ライセンスの割り当て
author: DaniEASmith
ms.author: danismith
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Microsoft Teams for Educationのライセンスを割り当てる方法について説明します。
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom:
- admindeeplinkMAC
ms.openlocfilehash: e57780436167e3a872e78a717d12cd3acc35a6e9
ms.sourcegitcommit: c19ac3be42cc4b8409c8d512bbe3156736af0309
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/24/2022
ms.locfileid: "67426804"
---
# <a name="assign-microsoft-teams-licenses-for-education"></a>教育機関向けの Microsoft Teams ライセンスの割り当て

この記事は、教職員、学生にチーム ライセンスを割り当てる必要がある教育の IT 管理者向けです。

ユーザーに Teams の準備をさせるには、次の手順を実行する必要があります。

1. [Microsoft 365 管理センターで学校の Microsoft Teams を有効にします](/microsoft-365/education/intune-edu-trial/enable-microsoft-teams)。
2. Teams を含む Microsoft 365 サービスにアクセスするためのライセンスをユーザー アカウントに割り当てます。

## <a name="ways-to-assign-teams-licenses"></a>Teams ライセンスを割り当てる方法

ユーザー アカウントには、次のいずれかのライセンスを割り当てることができます。

- 個別に、またはMicrosoft 365 管理センター内の少数のユーザー グループに対して。
- [PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell) または [Active Directory グループ ベースのライセンス](/azure/active-directory/users-groups-roles/licensing-groups-assign)を使用して、グループ メンバーシップを自動的に使用します。

この記事では、Microsoft 365 管理センターでライセンスを割り当てる方法について説明します。

Microsoft 365 管理センターでは、次のいずれかのユーザーにライセンスを割り当てることができます。

- 特定のユーザーに製品ライセンスを割り当てる [ **ライセンス]** ページ。
- ユーザーのライセンスを特定の製品に割り当てる **[アクティブなユーザー]** ページ。

> [!NOTE]
> グローバル管理者、課金管理者、ライセンス管理者、またはユーザー管理の管理者のいずれかである必要があります。詳細については、「[Office 365 の管理者ロールについて](/microsoft-365/admin/add-users/about-admin-roles)」を参照してください。

## <a name="assign-licenses-to-users-on-the-licenses-page"></a>ライセンス ページでユーザーにライセンスを割り当てる

**[ライセンス**] ページには、サブスクリプションがあるすべての製品、各製品のライセンスの合計数、割り当てられているライセンスの数、使用可能なライセンスの数の一覧が表示されます。

1. [管理センター](https://go.microsoft.com/fwlink/p/?linkid=2024339)の [**課金** > [ライセンス](https://go.microsoft.com/fwlink/p/?linkid=842264)] ページに移動します。

2. ライセンスを割り当てる製品を選択します。 Microsoft Teams は、Students SKU の無料Microsoft 365 A1の一部です。

3. [**ライセンスの割り当て**] を選択します。

4. [**ユーザーへのライセンスの割り当て**] ウィンドウで、名前を入力し始めます。名前のリストが作られて表示されるはずです。

5. 表示された結果から目的の名前を選択し、リストに追加します。 最大 20 人のユーザーを同時に追加できます。

6. Microsoft Teams など、特定のアイテムへのアクセス権の割り当てまたは削除を行うには、[**アプリとサービスのオン/オフの切り替え**] を選択します。 [**Microsoft Teams**] と [**Office for the web (Education)**] が選択されていることを確認してください。

7. 完了したら、[**割り当て**] を選択し、[**閉じる**] を選択します。

### <a name="change-the-apps-and-services-a-user-has-access-to"></a>ユーザーがアクセスできるアプリとサービスを変更する

1. 目的のユーザーが含まれている行を選択します。

2. 右側のウィンドウで、アクセス権の付与または削除を行うアプリとサービスを選択または選択解除します。

3. 完了したら、[**保存**] を選択し、[**閉じる**] を選択します。

## <a name="assign-licenses-to-users-on-the-active-users-page"></a>[アクティブなユーザー] ページでユーザーにライセンスを割り当てる

1. [管理センター](https://go.microsoft.com/fwlink/p/?linkid=2024339)で、[**ユーザー** > [アクティブ ユーザー](https://go.microsoft.com/fwlink/p/?linkid=834822)] ページに移動します。

2. ライセンスを割り当てるユーザー名の横にある丸を選択します。

3. 上部にある [ **製品ライセンスの管理**] を選択します。

4. [**製品ライセンスの管理**] ウィンドウで、[**既存の製品ライセンスの割り当てに追加**] > [**次へ**] の順に選択します。

5. [**既存の製品に追加**] ウィンドウで、選択したユーザーに付与するライセンスのトグルを [**オン**] の位置に切り替えます。 [**Microsoft Teams**] と [**Office for the web (Education)**] が選択されていることを確認してください。

   既定により、これらのライセンスに関連付けられているすべてのサービスがユーザーに自動的に割り当てられます。 ユーザーが利用できるサービスを制限できます。 ユーザーに使用させないサービスのトグルを [**オフ**] の位置に切り替えます。

6. ウィンドウの下部にある [**閉じる****の追加** > ] を選択します。
