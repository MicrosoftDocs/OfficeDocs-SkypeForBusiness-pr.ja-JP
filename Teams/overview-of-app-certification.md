---
title: Microsoft によるアプリ認定の概要
ms.reviewer: ''
description: サード パーティ製アプリのセキュリティ用 Microsoft 365 アプリ コンプライアンス プログラム、コンプライアンス、プライバシーについて説明します。
ms.topic: article
author: guptaashish
ms.author: guptaashish
manager: prkosh
audience: admin
ms.date: 04/05/2022
ms.service: msteams
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
ms.localizationpriority: high
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 86da9e6284c5fd295a1fee8894ec61734b2ebe1e
ms.sourcegitcommit: 9946c6c1faa78617ccd7bdf115457090ebce5619
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/21/2022
ms.locfileid: "66190626"
---
# <a name="microsoft-365-app-compliance-program-for-security-compliance-and-privacy-of-third-party-apps"></a>サード パーティ製アプリのセキュリティ用 Microsoft 365 アプリ コンプライアンス プログラム、コンプライアンス、プライバシー

Microsoft コンプライアンス プログラムは、主要な業界標準のフレームワークから派生したコントロールに対してアプリをチェックし、監査します。 プログラムは、顧客データを保護するために強力なセキュリティとコンプライアンスのプラクティスが実施されていることを示します。 プログラムには、次のフェーズがあります。

* 発行元の検証。
* 発行元の構成証明。
* Microsoft 365 認定。

## <a name="publisher-verification"></a>発行元の検証

アプリ開発者がアプリを Microsoft に送信する前に、開発者は検証を受ける必要があります。 発行元は、Microsoft パートナー ネットワーク (MPN) アカウントを使用して ID を確認し、この MPN アカウントをアプリの登録に関連付けます。 発行元の検証は、管理者とエンド ユーザーがアプリケーション開発者の信頼性について理解するのに役立ちます。 発行元の検証には、次のような利点があります。

* 顧客への透明性の強化とリスクの軽減 - この機能は、組織で使用されているどのアプリが信頼できる開発者によって公開されているかを顧客が理解するのに役立ちます。
* ブランドの強化 - Azure Active Directory の同意プロンプト、Enterprise アプリ ページ、エンドユーザーと管理者が使用するその他のユーザー インターフェイスに `verified` バッジが表示されます。
* よりスムーズなエンタープライズ導入 - 管理者は、発行元の検証状態をプライマリ ポリシー条件として、ユーザー同意ポリシーを構成できます。

## <a name="publisher-attestation"></a>発行元の構成証明

発行元による構成証明は、アプリ コンプライアンス プログラムの次の層です。 発行元によって構成証明されたアプリは、アプリのセキュリティとコンプライアンスの対策について管理者に信頼感を与えます。 また、アプリのこの情報を確認する時間を短縮するのにも役立ちます。 構成証明には、[Microsoft Cloud App Security](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/cloud-app-security) によって識別された 80 を超えるリスク要因に対するアプリのセキュリティ、データ処理、コンプライアンス プラクティスが反映されます。 発行元の検証が完了する前に、発行元の構成証明プロセスを開始できます。

アプリ開発者は、アプリのセキュリティとコンプライアンスを評価するために顧客と IT 管理者からよく寄せられる質問を含む自己評価を完了するように求められます。 その後、より簡単でタイムリーな評価のため、Microsoft はこの情報を公開します。 詳細については、「[構成証明ガイド](/microsoft-365-app-certification/docs/enterprise-app-attestation-guide)」を参照してください。

管理者は、3 つの方法で、発行元によって構成証明されたアプリをすばやく確認できます。

* アプリに関する詳細情報を収集する場合、「[Microsoft Teams アプリのセキュリティとコンプライアンス](/microsoft-365-app-certification/teams/teams-apps)」で、特定のアプリのリンクで詳細を確認するか、Teams 管理センターで発行元の構成証明リンクを選択します。

  :::image type="content" source="media/attested-app-tac3.png" alt-text="Teams 管理センターで、発行元による構成証明リンクをクリックして、アプリの構成証明の詳細を表示します":::

* Teams 管理センターで、**[アプリの管理]** ページからアプリの詳細を確認する場合、アプリの詳細ページのバナーにある発行元による構成証明済みアイコンを参照してください。

  :::image type="content" source="media/attested-app-tac1.png" alt-text="Teams 管理センターでは、構成証明されたすべてのアプリに発行元による構成証明済みアイコンが表示されます。":::

* Teams 管理センターでアプリにアクセス許可を付与する場合、アプリ名の前に青いチェックマークが付いていると、アプリが発行元によって構成証明されたアプリと、Microsoft 365 認定されたアプリのどちらであるかを示します。

   :::image type="content" source="media/attested-app-tac2.png" alt-text="Teams 管理センターの、アクセス許可を付与するダイアログの青いチェックマークは、発行元によって構成証明されたアプリを示しています。":::

構成証明または認定されたアプリの構成証明の詳細ページには、次の詳細が一覧表示されます。

:::image type="content" source="media/attested-app-doc-details.png" alt-text="構成証明されたアプリに関して提供された詳細情報。":::

## <a name="microsoft-365-certification"></a>Microsoft 365 認定

アプリの認定は、次の方法で達成されます。

* 資格のあるアナリストのレビュー。
* アプリのセキュリティとコンプライアンスのフレームワーク、プロセス、および手順を中心とした包括的な評価の承認。

主要な業界標準のフレームワークから派生した一連のセキュリティ コントロールに対してアプリをチェックします。

証明書は、アプリが組織でアクティブ化されたときに、顧客データを保護するために強力なセキュリティとコンプライアンスのプラクティスが実施されていることを示します。 Microsoft 365 認定が管理者およびエンドユーザーにとってどのように役立つかについての詳細は、「[Microsoft 365 アプリ コンプライアンス プログラム](/microsoft-365-app-certification/docs/enterprise-app-certification-guide)」の [概要] を参照してください。

管理者は、次の方法で Microsoft 365 認定アプリをすばやく確認できます。

* Web 上のアプリに関する詳細情報を収集する場合は、アプリに関する Microsoft ドキュメントのシールド アイコンを参照してください。

  :::image type="content" source="media/attested-app-doc-details.png" alt-text="アプリのセキュリティとコンプライアンスに関する詳細なヘルプ記事で、Microsoft 365 認定情報を確認してください":::

* Teams 管理センターでアプリケーションを確認する場合は、[認定] 列を使用してアプリの一覧を並べ替えます。 アイコンを参照し、必要に応じてリンクを選択して、上記のアプリ固有のページにアクセスします。

  :::image type="content" source="media/m365cert-apps-list1.png" alt-text="Teams 管理センターでアプリの Microsoft 365 認定ステータスを表示します。" lightbox="media/m365cert-apps-list2.png":::

* アプリの詳細を表示するときは、アプリ バナーの Microsoft3 65 認定アイコンを参照してください。

  :::image type="content" source="media/m365cert-app-details-banner.png" alt-text="Teams 管理センターで特定のアプリを管理するときに、アプリ バナーで Microsoft 365 認定情報を表示する":::

* Teams 管理センターでアプリにアクセス許可を付与する場合、アプリ名の前に青いチェックマークが付いていると、アプリが発行元によって構成証明されたアプリと、Microsoft 365 認定されたアプリのどちらであるかを示します。

   :::image type="content" source="media/attested-app-tac2.png" alt-text="管理者は、アプリが Microsoft 365 認定証明がされていることを確認するため、Teams 管理センターのアクセス許可を付与するダイアログで青いチェックマークをオンにできます":::

## <a name="view-security-compliance-and-privacy-information"></a>セキュリティ、コンプライアンス、プライバシーの情報を表示する

Microsoft ドキュメントと Teams 管理センターでは、構成証明されたアプリまたは認定済みアプリのセキュリティ、プライバシー、コンプライアンス、および動作に関する情報を確認できます。

### <a name="microsoft-documentation"></a>Microsoft ドキュメント

リストされている各アプリのセキュリティ、プライバシー、コンプライアンスなどの詳細は、「[Microsoft Teams アプリのセキュリティとコンプライアンス](/microsoft-365-app-certification/teams/teams-apps)」からリンクされているアプリ固有のヘルプ記事に記載されています。

:::image type="content" source="media/attested-app-doc-details.png" alt-text="Microsoft コンプライアンス プログラムを受けるアプリに関して提供される詳細情報。":::

### <a name="teams-admin-center"></a>Teams 管理センター

組織のアプリを評価するときは、Microsoft Cloud App Security (MCAS) などの独立した Cloud Access Security Brokers (CASB) を使用して、アプリのセキュリティと動作に関する情報を見つけることができます。 Teams 管理センターには、Microsoft 365 認定アプリの MCAS からのセキュリティとコンプライアンスの情報が含まれているため、アプリがニーズを満たしているかどうかを確認できます。

> [!NOTE]
> この機能は、組織が MCAS をサポートするライセンスを持っているかどうかにかかわらず、すべての管理者が利用できます。

アプリの MCAS 情報にアクセスするには:

1. Teams 管理センターで、**[Teams アプリ]** の **[アプリの管理]** を選択します。
1. **[認定]** を選択してアプリを並べ替え、すべての Microsoft 365 認定アプリをテーブルの一番上にプッシュします。
1. Microsoft 365 認定アプリを選択します。
1. **[セキュリティとコンプライアンス]** タブを選択します。

   :::image type="content" source="media/mcas.png" alt-text="Teams 管理センターの [セキュリティとコンプライアンス] タブを示すスクリーンショット":::

   アプリでサポートされている機能の詳細を取得するには、各カテゴリのドロップダウン リストを選択します。

<!--- TBD: Move to the permissions article 

## View the granted Graph permissions in Azure Portal

Admins can grant permission to an app on behalf of all organization users. It helps avoid each user to individually request the permissions. Permissions granted of an admin are called delegated permissions in [Azure Portal](https://aad.portal.azure.com/).

Before you grant any permission to an app, review a list of requested permissions in the [Manage Apps](https://admin.teams.microsoft.com/policies/manage-apps) section of Teams admin center.

:::image type="content" source="media/attested-app-tac2.png" alt-text="In Teams admin center, on the dialog to grant permissions, admins can check the permissions requested by an app.":::

After admins grant the org-wide permissions to an app, they can review the Graph permissions in Azure Portal.

:::image type="content" source="media/tac-perms-in-aad-after-granting1.png" alt-text="Admins can see all the app permissions granted by users and admins in the Azure Portal." lightbox="media/tac-perms-in-aad-after-granting2.png":::
--->

## <a name="view-privacy-policy-and-terms-of-use-of-an-app"></a>アプリのプライバシー ポリシーと利用規約を表示する

Teams 管理センターの各アプリのページには、アプリのプライバシーに関する声明と利用規約へのリンクが含まれています。

:::image type="content" source="media/tac-app-tou-privacy-info1.png" alt-text="管理者は、Teams 管理センターから、すべてのアプリのプライバシー ポリシーと利用規約へのリンクにアクセスできます" lightbox="media/tac-app-tou-privacy-info2.png":::

<!--- TBD: Parking some content for later review. Check if this content needs to be published.

- How to view the support information for an app in TAC?

- We also have a few more quality and security checks for apps. We have launched Microsoft Cloud App Security (MCAS) program for the customer who have E5 or EMS license, where we rate risk for your cloud apps based on regulatory certification, industry standards, and best practices. We are also working on an Apps Quality Score system (launching soon) for all apps on Teams platform, and you will be able to check an app’s quality score quickly on Teams Store.

--->

## <a name="see-also"></a>関連項目

* [アプリのアクセス許可を表示し、管理者の同意を付与します](app-permissions-admin-center.md)。
