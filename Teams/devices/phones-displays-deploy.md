---
title: Intuneを使用して Android で Teams の電話、Teams のディスプレイ、Teams パネル、Microsoft Teams Roomsを展開する
author: CarolynRowe
ms.author: crowe
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
- Teams_ITAdmin_Devices
search.appverid: MET150
ms.localizationpriority: medium
description: この記事では、Microsoft Teams Android デバイスでサポートされている機能の概要と機能について説明します。
ms.openlocfilehash: ef30268ef966eca00a75a583c9acb6ae608a7a81
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2022
ms.locfileid: "67267802"
---
# <a name="deploy-teams-phones-teams-displays-teams-panels-and-microsoft-teams-rooms-on-android-using-intune"></a>Intuneを使用して Android で Teams の電話、Teams のディスプレイ、Teams パネル、Microsoft Teams Roomsを展開する

この記事では、Intuneを使用して Android で Teams の電話、Teams ディスプレイ、Teams パネル、Microsoft Teams Roomsを展開する方法の概要について説明します。

## <a name="conditional-access"></a>条件付きアクセス

条件付きアクセスは、Office 365 リソースにアクセスするデバイスが適切に管理され、セキュリティで保護されていることを確認するのに役立つ Azure Active Directory (Azure AD) 機能です。  Teams サービスに条件付きアクセス ポリシーを適用する場合、Teams にアクセスする Android デバイス (Teams スマートフォン、Teams ディスプレイ、Teams パネル、Android のMicrosoft Teams Roomsを含む) は、Intuneに登録する必要があり、その設定はポリシーに準拠している必要があります。  デバイスがIntuneに登録されていない場合、またはデバイスが登録されているが、その設定がポリシーに準拠していない場合、条件付きアクセスにより、ユーザーがデバイスで Teams アプリにサインインしたり、Teams アプリを使用したりできなくなります。

通常、Intune内で定義されたコンプライアンス ポリシーは、ユーザーのグループに割り当てられます。  つまり、Android コンプライアンス ポリシーを user@contoso.com に割り当てると、そのポリシーは Android スマートフォンと、user@contoso.com サインインするすべての Android ベースの Teams デバイスに同じように適用されます。

条件付きアクセスを使用する場合は、Intune登録を適用する必要があります。組織内では、Intune登録を正常に行えるように設定する必要があります。

- **Intune ライセンス** Teams デバイスにサインインするユーザーには、Intuneのライセンスが必要です。  Teams デバイスが有効なIntune ライセンスを持つユーザー アカウントにサインインしている限り、デバイスはサインイン プロセスの一環としてMicrosoft Intuneに自動的に登録されます。
- **Intuneを構成** する Android デバイス管理者登録用に適切に構成Intuneテナントが設定されている必要があります。

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a>Teams Android ベースのデバイスを登録するようにIntuneを構成する

Teams Android ベースのデバイスは、Android デバイス管理者 (DA) 管理を介してIntuneによって管理されます。 デバイスをIntuneに登録する前に、実行する基本的な手順がいくつかあります。  現在、Intuneを使用してデバイスを既に管理している場合は、これらの作業をすべて既に行っている可能性があります。  そうでない場合は、次の操作を行います。

> [!NOTE]
> - テナント管理者が共通領域の電話をIntuneに登録する場合は、アカウントにIntune ライセンスを追加し、Intune登録の手順に従う必要があります。
> - Teams デバイスへのサインインに使用したユーザー アカウントがIntuneのライセンスを取得していない場合は、Intuneコンプライアンス ポリシーと登録制限をアカウントに対して無効にする必要があります。



1. MDM (モバイル デバイス管理) 機関Intune設定します。  

   Intuneを使用したことがない場合は、デバイスを登録する前に MDM 機関を設定する必要があります。 詳細については、「 [モバイル デバイス管理機関の設定](/intune/fundamentals/mdm-authority-set)」を参照してください。  これは、新しいIntune テナントを作成するときに実行する必要がある 1 回限りの手順です。
1. Android デバイス管理者の登録を有効にします。
  
   Android ベースの Teams デバイスは、Intuneを使用してデバイス管理者デバイスとして管理されます。  新しく作成されたテナントの場合、デバイス管理者の登録は既定でオフになっています。 [Android デバイス管理者の登録](/intune/enrollment/android-enroll-device-administrator)を参照してください。
1. ユーザーにライセンスを割り当てます。 
 
   Intuneに登録している Teams デバイスのユーザーには、有効なIntune ライセンスが割り当てられている必要があります。 詳細については、「[Intuneにデバイスを登録できるように、ユーザーにライセンスを割り当てる](/intune/fundamentals/licenses-assign)」を参照してください。
1. デバイス管理者のコンプライアンス ポリシーを割り当てます。  

   1. Android デバイス管理者コンプライアンス ポリシーを作成します。

   1. Teams デバイスにサインインするユーザーを含む Azure Active Directory グループに割り当てます。 [コンプライアンス ポリシーを使用して、Intuneで管理するデバイスのルールを設定する方法](/mem/intune/protect/device-compliance-get-started)に関するページを参照してください。

## <a name="see-also"></a>関連項目

[Teams 対応の電話機](phones-for-teams.md)

[Microsoft Teams 認定 IP 電話](teams-ip-phones.md)

[Teams の表示](teams-displays.md)

[Teams でのデバイスの管理](device-management.md)

[Teams Marketplace](https://office.com/teamsdevices)
