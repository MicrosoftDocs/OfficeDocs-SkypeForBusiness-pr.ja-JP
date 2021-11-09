---
title: Intune Teams Android で携帯電話、Teamsディスプレイ、Microsoft Teams会議室をデプロイする
ms.author: v-mahoffman
author: HowlinWolf-92
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
description: この記事では、ディスプレイでサポートされる機能と機能の概要Microsoft Teamsします。
ms.openlocfilehash: 96ffaef167fd40b320ff4c1b9b7a6dca0e9c3325
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60861964"
---
# <a name="deploy-teams-phones-teams-displays-and-microsoft-teams-rooms-on-android-using-intune"></a>Intune Teams Android で携帯電話、Teamsディスプレイ、Microsoft Teams会議室をデプロイする

この記事では、Intune を使用して Android Teams、Teams、Microsoft Teams Rooms を展開する方法の概要について説明します。

## <a name="conditional-access"></a>条件付きアクセス

条件付きアクセスは、Azure Active Directory (Azure AD) 機能であり、Office 365 リソースにアクセスするデバイスが適切に管理され、セキュリティで保護されていることを確認するのに役立ちます。  Teams サービスに条件付きアクセス ポリシーを適用する場合、Teams にアクセスする Android デバイス (Teams スマートフォン、Teams ディスプレイ、Microsoft Teams Rooms on Android を含む) は Intune に登録する必要があります。その設定はポリシーに準拠する必要があります。  デバイスが Intune に登録されていない場合、またはデバイスが登録されているが、その設定がポリシーに準拠しない場合、条件付きアクセスでは、ユーザーがデバイスで Teams アプリにサインインまたは使用できません。

通常、Intune 内で定義されたコンプライアンス ポリシーは、ユーザーのグループに割り当てられます。  つまり、android コンプライアンス ポリシーを user@contoso.com に割り当てると、そのポリシーは Android スマートフォンと、サインインする Android ベースの Teams デバイスにも同様 user@contoso.com 適用されます。

Intune 登録を適用する必要がある条件付きアクセスを使用する場合、組織では、Intune 登録を正常に行うには、次の 2 つの設定が必要です。

- **Intune ライセンス** デバイスにサインインするユーザー Teams Intune のライセンスが必要です。  Teams デバイスが有効な Intune ライセンスを持つユーザー アカウントにサインインしている限り、デバイスはサインイン プロセスの一環として Microsoft Intune に自動的に登録されます。
- **Intune の構成** Android デバイス管理者登録用に適切に構成された Intune テナントが設定されている必要があります。

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a>Android ベースのデバイスにTeams Intune を構成する

TeamsAndroid ベースのデバイスは、Android デバイス管理者 (DA) 管理を介して Intune によって管理されます。 デバイスを Intune に登録する前に、いくつかの基本的な手順を実行します。  現在 Intune でデバイスを既に管理している場合は、既にこれらすべてのことを行っている可能性があります。  ない場合は、次の操作を行います。

> [!NOTE]
> - テナント管理者が共通領域の電話を Intune に登録する場合は、Intune ライセンスをアカウントに追加し、Intune 登録の手順に従う必要があります。
> - Teams デバイスへのサインインに使用したユーザー アカウントが Intune のライセンスを取得されていない場合は、Intune コンプライアンス ポリシーと登録制限をアカウントで無効にする必要があります。



1. Intune MDM (モバイル デバイス管理) 機関を設定します。  

   Intune を使用したことがない場合は、デバイスを登録する前に MDM 機関を設定する必要があります。 詳細については、「モバイル デバイス管理 [機関を設定する」を参照してください](/intune/fundamentals/mdm-authority-set)。  これは、新しい Intune テナントを作成するときに実行する必要がある 1 回の手順です。
1. Android デバイス管理者登録を有効にします。
  
   Android ベースのTeamsデバイスは、Intune を使用してデバイス管理者デバイスとして管理されます。  新しく作成されたテナントでは、デバイス管理者の登録は既定でオフになっています。 「Android [デバイス管理者の登録」を参照してください](/intune/enrollment/android-enroll-device-administrator)。
1. ユーザーにライセンスを割り当てる。 
 
   Intune にTeamsデバイスのユーザーには、有効な Intune ライセンスが割り当てられている必要があります。 詳細については、「ユーザーが Intune にデバイスを [登録できるようライセンスをユーザーに割り当てる」を参照してください](/intune/fundamentals/licenses-assign)。
1. デバイス管理者のコンプライアンス ポリシーを割り当てる。  

   1. Android デバイス管理者のコンプライアンス ポリシーを作成します。

   1. デバイスにサインインするAzure Active Directoryを含むグループに割り当Teamsします。 [「コンプライアンス ポリシーを使用して Intune で管理するデバイスのルールを設定する」を参照してください](/mem/intune/protect/device-compliance-get-started)。

## <a name="see-also"></a>関連項目

[Teams 対応の電話機](phones-for-teams.md)

[Microsoft Teams 認定 IP 電話](teams-ip-phones.md)

[Teams表示](teams-displays.md)

[Teams でのデバイスの管理](device-management.md)

[Teams Marketplace](https://office.com/teamsdevices)
