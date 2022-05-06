---
title: Microsoft Teams Roomsの条件付きアクセスとコンプライアンスのベスト プラクティス
ms.author: czawideh
author: cazawideh
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: 推奨される条件付きアクセスとIntuneデバイス コンプライアンス ポリシーとMicrosoft Teams Roomsのベスト プラクティスについて説明します。
ms.openlocfilehash: 1f4bec9d47b73be1638b1740afeb879b4dfb4026
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/16/2022
ms.locfileid: "63689140"
---
# <a name="conditional-access-and-intune-compliance-for-microsoft-teams-rooms"></a>Microsoft Teams Roomsの条件付きアクセスとIntuneコンプライアンス

この記事では、共有スペースで使用されるMicrosoft Teams Roomsの条件付きアクセスポリシーとIntuneデバイス コンプライアンス ポリシーの要件とベスト プラクティスについて説明します。

## <a name="requirements"></a>要件

Teams Roomsは、条件付きアクセス ポリシーを割り当てるデバイスに既にデプロイされている必要があります。 Teams Roomsまだデプロイしていない場合は、「[会議室と共有Teamsデバイスのリソース アカウントを作成](with-office-365.md)する」と [Android でのMicrosoft Teams Roomsのデプロイ](../devices/collab-bar-deploy.md)に関するページを参照してください。

条件付きアクセスを使用するには、Azure Active Directory P1 サービス プランが必要です。 Microsoft Teams Rooms ライセンスに含まれています。

## <a name="teams-rooms-conditional-access-best-practices"></a>条件付きアクセスのベスト プラクティスをTeams Roomsする

条件付きアクセス ポリシーは、共有スペース内にあり、複数のユーザーが使用するデバイスでサインイン プロセスをセキュリティで保護できます。 Azure Active Directoryの条件付きアクセス (Azure AD) の概要については、「[Azure Active Directoryの条件付きアクセスとは](/azure/active-directory/conditional-access/overview)」を参照してください。

条件付きアクセスを使用してTeams Roomsをセキュリティで保護する場合は、次のベスト プラクティスを検討してください。

-   デプロイと管理を簡略化するには、Teams Roomsに関連付けられているすべてのMicrosoft 365ルーム リソース アカウントを 1 つのユーザー グループに含めます。

-   すべてのTeams Roomsリソース アカウントの名前付け標準を持ちます。 たとえば、アカウント名 'mtr-room1@contoso.com' と 'mtr-room2@contoso.com' はどちらもプレフィックス 'mrt-' で始まります。
    アカウント名が標準化されている場合は、Azure ADの動的グループを使用して、これらのすべてのアカウントに条件付きアクセス ポリシーを一度に自動的に適用できます。 [動的グループの詳細については、「動的に設定されたグループ メンバーシップの規則](/azure/active-directory/enterprise-users/groups-dynamic-membership)」を参照してください。

Teams Roomsでサポートされている条件付きアクセスの割り当ての一覧については、「[サポートされている条件付きアクセス ポリシー](supported-ca-and-compliance-policies.md#supported-conditional-access-policies)」を参照してください。

## <a name="example-conditional-access-policy"></a>条件付きアクセス ポリシーの例

次の例では、条件付きアクセス ポリシーは次のように機能します。

1.  アカウントサインインは、特定のユーザー グループのメンバーである必要があります。この例では、"共有デバイス" グループです。

2.  アカウントサインインは、Exchange Online、Microsoft Teams、またはオンラインSharePointへのアクセスのみを試行している必要があります。 他のクライアント アプリへのサインインは拒否されます。

3.  リソース アカウントは、Windows デバイス プラットフォームでサインインしている必要があります。

4.  リソース アカウントは、既知の信頼できる場所からサインインする必要もあります。

これらの条件が正常に満たされ、ユーザーが正しいユーザー名とパスワードを入力した場合、リソース アカウントはTeamsにサインインします。

## <a name="conditional-access-with-microsoft-intune-compliance-for-teams-rooms"></a>Teams RoomsのMicrosoft Intuneコンプライアンスを使用した条件付きアクセス

コンプライアンス要件は、オペレーティング システムの最小バージョンなど、デバイスが準拠としてマークするために満たす必要がある定義された規則です。 デバイスは、リソース アカウントへのサインインに使用する前に、準拠していると見なす必要があります。

Teams RoomsでサポートされているIntuneコンプライアンス ポリシーの一覧については、「[サポートされているデバイス コンプライアンス ポリシー](supported-ca-and-compliance-policies.md#supported-device-compliance-policies)」を参照してください。

Teams Android デバイスでIntuneを設定する方法の詳細については、「Android ベースのデバイス[を登録するIntune Teams構成](../devices/phones-displays-deploy.md#configure-intune-to-enroll-teams-android-based-devices)する」を参照してください。

## <a name="example-windows-only-conditional-access-with-intune-device-compliance"></a>例 (Windowsのみ): Intune デバイスコンプライアンスを使用した条件付きアクセス

この例では、WindowsのTeams Rooms

1. Windows上のTeams Roomsでファイアウォールが実行されていることを要求します。

2. Microsoft Defender がTeams Roomsで実行されていることを要求します。

3. Teams ルームがこれらの要件のいずれかを満たしていない場合、その会議室は準拠としてマークされ、デバイスはサインインしません。

このコンプライアンス ポリシーは、リソース アカウントだけでなく、すべてのユーザー Teams適用されます。
