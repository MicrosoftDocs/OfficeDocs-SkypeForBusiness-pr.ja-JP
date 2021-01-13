---
title: Intune を使用して Teams の電話と Teams のディスプレイを展開する
ms.author: v-cichur
author: cichur
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
localization_priority: Normal
description: この記事では、Microsoft Teams のディスプレイでサポートされる機能の概要と機能について説明します。
ms.openlocfilehash: 4d955db2f260af0eff3d0c1f059461703cf23d79
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825417"
---
# <a name="deploy-teams-phones-and-teams-displays-using-intune"></a>Intune を使用して Teams の電話と Teams のディスプレイを展開する

この記事では、Intune を使用して Teams 電話機と Teams ディスプレイを展開する方法の概要を示します。

## <a name="conditional-access"></a>条件付きアクセス

条件付きアクセスは Azure Active Directory (Azure AD) 機能であり、Office 365 リソースにアクセスするデバイスが適切に管理され、セキュリティで保護されていることを確認するのに役立ちます。  Teams サービスに条件付きアクセス ポリシーを適用する場合、Teams にアクセスする Android デバイス (Teams の携帯電話や Teams を含む) は Intune に登録する必要があります。また、その設定はポリシーに準拠する必要があります。  デバイスが Intune に登録されていない場合、またはデバイスが登録されているが、その設定がポリシーに準拠しない場合、条件付きアクセスにより、ユーザーはデバイスで Teams アプリにサインインしたり使用したりできません。

通常、Intune 内で定義されたコンプライアンス ポリシーはユーザーのグループに割り当てられます。  つまり、Android コンプライアンス ポリシーを user@contoso.com に割り当てると、そのポリシーは Android スマートフォンと、サインインしている任意の Android ベースの Teams user@contoso.com適用されます。

Intune の登録を適用する必要がある条件付きアクセスを使用する場合は、組織で Intune の登録を正常に行うには、次の 2 つの設定が必要です。

- **Intune ライセンス** Teams デバイスにサインインするユーザーには、Intune のライセンスが必要です。  Teams デバイスが有効な Intune ライセンスを持つユーザー アカウントにサインインしている限り、デバイスはサインイン プロセスの一環として Microsoft Intune に自動的に登録されます。
- **Intune を構成する** Android デバイス管理者登録用に適切に構成された Intune テナントが必要です。

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a>Teams Android ベースのデバイスを登録するために Intune を構成する

Teams Android ベースのデバイスは、Android デバイス管理者 (DA) 管理を介して Intune で管理されます。 デバイスを Intune に登録する前に、いくつかの基本的な手順を実行します。  Intune でデバイスを管理している場合は、既にこれらすべてのことを行っている可能性があります。  表示されない場合は、次の操作を行います。

1. Intune MDM (モバイル デバイス管理) 機関を設定します。  Intune を使用したことがない場合は、デバイスを登録する前に MDM 機関を設定する必要があります。 詳細については、「モバイル デバイス管理 [機関を設定する」を参照してください](https://docs.microsoft.com/intune/fundamentals/mdm-authority-set)。  これは、新しい Intune テナントを作成する際に実行する必要がある 1 回の手順です。
2. Android デバイス管理者の登録を有効にします。 Android ベースの Teams デバイスは、Intune を使用してデバイス管理者デバイスとして管理されます。  新しく作成されたテナントでは、デバイス管理者の登録は既定でオフになっています。  詳細については、Android デバイス管理者 [の登録を参照してください](https://docs.microsoft.com/intune/enrollment/android-enroll-device-administrator)。
3. ライセンスをユーザーに割り当てる。 Intune に登録している Teams デバイスのユーザーには、有効な Intune ライセンスが割り当てられている必要があります。 詳細については、「Intune にデバイスを登録 [するためにライセンスをユーザーに割り当てる」を参照してください](https://docs.microsoft.com/intune/fundamentals/licenses-assign)。
4. デバイス管理者のコンプライアンス ポリシーを割り当てる。  Android デバイス管理者コンプライアンス ポリシーを作成し、Teams デバイスにサインインするユーザーを含む Azure Active Directory グループに割り当てる。 詳細については、「コンプライアンス ポリシーを使用して、Intune で管理するデバイスのルール [を設定する」を参照してください](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started)。

## <a name="see-also"></a>関連項目

[Teams 対応の電話機](phones-for-teams.md)

[Microsoft Teams 認定 IP 電話](teams-ip-phones.md)

[Teams の表示](teams-displays.md)

[Teams でのデバイスの管理](device-management.md)

[Teams Marketplace](https://office.com/teamsdevices)
