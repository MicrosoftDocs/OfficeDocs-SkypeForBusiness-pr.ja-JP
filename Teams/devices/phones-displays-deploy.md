---
title: Intuneを使用してTeams電話、Teamsディスプレイ、Teams パネル、Microsoft Teams RoomsをAndroidに展開する
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: weizxue
ms.topic: reference
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
search.appverid: MET150
ms.localizationpriority: medium
description: この記事では、Microsoft Teams Android デバイスでサポートされている機能の概要と機能について説明します。
ms.openlocfilehash: 17f5e537b44d3aacd967ff5e8ffaa84df9da3f9b
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674859"
---
# <a name="deploy-teams-phones-teams-displays-teams-panels-and-microsoft-teams-rooms-on-android-using-intune"></a>Intuneを使用してTeams電話、Teamsディスプレイ、Teams パネル、Microsoft Teams RoomsをAndroidに展開する

この記事では、Intuneを使用してAndroidにTeams電話、Teamsディスプレイ、Teams パネル、Microsoft Teams Roomsを展開する方法の概要について説明します。

## <a name="conditional-access"></a>条件付きアクセス

条件付きアクセスは、Office 365 リソースにアクセスするデバイスが適切に管理され、セキュリティで保護されていることを確認するのに役立つ、Azure Active Directory (Azure AD) 機能です。  条件付きアクセス ポリシーをTeams サービスに適用する場合、Teams電話、Teamsディスプレイ、Teams パネル、AndroidのMicrosoft Teams Roomsを含む) Teamsに登録する必要があるデバイスをAndroidします。Intuneとその設定は、ポリシーに準拠している必要があります。  デバイスがIntuneに登録されていない場合、またはデバイスが登録されているが、その設定がポリシーに準拠していない場合、条件付きアクセスにより、ユーザーがデバイスでTeams アプリにサインインしたり、Teams アプリを使用したりできなくなります。

通常、Intune内で定義されたコンプライアンス ポリシーは、ユーザーのグループに割り当てられます。  つまり、Android コンプライアンス ポリシーを user@contoso.com に割り当てると、そのポリシーはAndroidスマートフォンとサインイン user@contoso.com AndroidベースのTeams デバイスに等しく適用されます。

条件付きアクセスを使用する場合は、Intune登録を適用する必要があります。組織内では、Intune登録を正常に行えるように設定する必要があります。

- **Intune ライセンス** Teams デバイスにサインインするユーザーは、Intuneに対してライセンスが付与されている必要があります。  Teams デバイスが有効なIntune ライセンスを持つユーザー アカウントにサインインしている限り、デバイスはサインイン プロセスの一環としてMicrosoft Intuneに自動的に登録されます。
- **Intuneを構成** するには、デバイス管理者の登録用に適切に構成IntuneテナントAndroid設定する必要があります。

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a>Teams Android ベースのデバイスを登録するようにIntuneを構成する

Teams Android ベースのデバイスは、Android デバイス管理者 (DA) 管理を介してIntuneによって管理されます。 デバイスをIntuneに登録する前に、実行する基本的な手順がいくつかあります。  現在、Intuneを使用してデバイスを既に管理している場合は、これらの作業をすべて既に行っている可能性があります。  そうでない場合は、次の操作を行います。

> [!NOTE]
> - テナント管理者が共通領域の電話をIntuneに登録する場合は、アカウントにIntune ライセンスを追加し、Intune登録の手順に従う必要があります。
> - Teams デバイスへのサインインに使用したユーザー アカウントがIntuneのライセンスを取得していない場合は、Intuneコンプライアンス ポリシーと登録制限をアカウントに対して無効にする必要があります。



1. MDM (モバイル デバイス管理) 機関Intune設定します。  

   Intuneを使用したことがない場合は、デバイスを登録する前に MDM 機関を設定する必要があります。 詳細については、「 [モバイル デバイス管理機関の設定](/intune/fundamentals/mdm-authority-set)」を参照してください。  これは、新しいIntune テナントを作成するときに実行する必要がある 1 回限りの手順です。
1. デバイス管理者の登録Android有効にします。
  
   Android ベースのTeams デバイスは、Intuneを使用してデバイス管理者デバイスとして管理されます。  新しく作成されたテナントの場合、デバイス管理者の登録は既定でオフになっています。 [デバイス管理者の登録Android参照してください](/intune/enrollment/android-enroll-device-administrator)。
1. ユーザーにライセンスを割り当てます。 
 
   Intuneに登録しているTeamsデバイスのユーザーには、有効なIntune ライセンスを割り当てる必要があります。 詳細については、「[Intuneにデバイスを登録できるように、ユーザーにライセンスを割り当てる](/intune/fundamentals/licenses-assign)」を参照してください。
1. デバイス管理者のコンプライアンス ポリシーを割り当てます。  

   1. Androidデバイス管理者コンプライアンス ポリシーを作成します。

   1. Teams デバイスにサインインするユーザーを含むAzure Active Directory グループに割り当てます。 [コンプライアンス ポリシーを使用して、Intuneで管理するデバイスのルールを設定する方法](/mem/intune/protect/device-compliance-get-started)に関するページを参照してください。

## <a name="see-also"></a>関連項目

[Teams 対応の電話機](phones-for-teams.md)

[Microsoft Teams 認定 IP 電話](teams-ip-phones.md)

[Teams表示](teams-displays.md)

[Teams でのデバイスの管理](device-management.md)

[Teams Marketplace](https://office.com/teamsdevices)
