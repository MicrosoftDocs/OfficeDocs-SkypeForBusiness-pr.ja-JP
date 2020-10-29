---
title: Intune を使用してチームの電話とチームの表示を展開する
ms.author: v-lanac
author: lanachin
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
description: この記事では、Microsoft Teams でサポートされている機能の概要について説明します。
ms.openlocfilehash: acebf619d76cd6df2f0da305deedec9dd3b79aa0
ms.sourcegitcommit: e07b2d7470b93e52b9e85207db0d6fa3a136efd9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/28/2020
ms.locfileid: "48787638"
---
# <a name="deploy-teams-phones-and-teams-displays-using-intune"></a>Intune を使用してチームの電話とチームの表示を展開する

この記事では、Intune を使用して、チームの電話やチームの表示を展開する方法の概要について説明します。

## <a name="conditional-access"></a>条件付きアクセス

条件付きアクセスは、Office 365 リソースにアクセスするデバイスが適切に管理され、セキュリティで保護されるようにするために、Azure Active Directory (Azure AD) の機能です。  条件付きアクセスポリシーを Teams サービスに適用すると、Access Teams は Intune に登録され、その設定がポリシーに準拠する必要があることを示す、Android デバイス (Teams の電話やチームの表示など) が必要になります。  デバイスが Intune に登録されていない場合、または登録されているが、その設定がポリシーに準拠していない場合は、条件付きアクセスによって、ユーザーがデバイスで Teams アプリにサインインしたり、使用したりすることを防ぐことができます。

通常、Intune で定義されているコンプライアンスポリシーは、ユーザーのグループに割り当てられます。  つまり、Android のコンプライアンスポリシーを user@contoso.com に割り当てると、そのポリシーは Android スマートフォンと、user@contoso.com によってサインインされる Android ベースの Teams デバイスに同じように適用されます。

Intune の登録を適用する必要がある条件付きアクセスを使用する場合、組織では、Intune 登録が成功するためにセットアップする必要があることがいくつかあります。

- **Intune ライセンス** Teams デバイスにサインインしているユーザーは、Intune のライセンスが必要です。  チームデバイスが有効な Intune ライセンスを持っているユーザーアカウントにサインインしている限り、そのデバイスはサインイン処理の一環として Microsoft Intune に自動的に登録されます。
- **Intune を構成する** Android デバイス管理者登録用に、適切に設定された Intune テナントが必要です。

## <a name="configure-intune-to-enroll-teams-android-based-devices"></a>Teams Android ベースのデバイスを登録するように Intune を構成する

Teams Android ベースのデバイスは、Intune で Android デバイス管理者 (DA) 管理によって管理されます。 デバイスを Intune に登録する前に、いくつかの基本的な手順を実行する必要があります。  既に Intune でデバイスを管理している場合は、次のことを行っている可能性があります。  そうでない場合は、次の操作を実行します。

1. Intune MDM (モバイルデバイス管理) 権限を設定します。  まだ Intune を使用していない場合は、デバイスを登録する前に MDM の権限を設定する必要があります。 詳細については、「 [モバイルデバイス管理機関を設定する](https://docs.microsoft.com/intune/fundamentals/mdm-authority-set)」を参照してください。  これは、新しい Intune テナントの作成時に行う必要がある1回限りの手順です。
2. Android デバイス管理者の登録を有効にします。 Android ベースの Teams デバイスは、Intune でデバイス管理デバイスとして管理されます。  新しく作成されたテナントの場合、デバイス管理者の登録は既定で無効になっています。  詳細については、「 [Android デバイス管理者の登録](https://docs.microsoft.com/intune/enrollment/android-enroll-device-administrator)」を参照してください。
3. ライセンスをユーザーに割り当てます。 Intune に登録しているチームデバイスのユーザーには、有効な Intune ライセンスが割り当てられている必要があります。 詳細については、「 [ユーザーにライセンスを割り当てて、ユーザーが Intune にデバイスを登録できるようにする](https://docs.microsoft.com/intune/fundamentals/licenses-assign)」を参照してください。
4. デバイス管理者のコンプライアンスポリシーを割り当てます。  Android デバイス管理者のコンプライアンスポリシーを作成して、チームデバイスにサインインするユーザーが含まれている Azure Active Directory グループに割り当てます。 詳細については、「 [コンプライアンスポリシーを使用して、Intune で管理しているデバイスのルールを設定する](https://docs.microsoft.com/mem/intune/protect/device-compliance-get-started)」を参照してください。

## <a name="see-also"></a>関連項目

[Teams 対応の電話機](phones-for-teams.md)

[Microsoft Teams 認定 IP 電話](teams-ip-phones.md)

[Teams の表示](teams-displays.md)

[Teams でのデバイスの管理](device-management.md)

[Teams Marketplace](https://office.com/teamsdevices)
