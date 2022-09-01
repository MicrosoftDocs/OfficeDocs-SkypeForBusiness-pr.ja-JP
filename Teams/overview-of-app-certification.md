---
title: Microsoft によるアプリ認定の概要
description: サード パーティ製アプリのセキュリティ用 Microsoft 365 アプリ コンプライアンス プログラム、コンプライアンス、プライバシーについて説明します。
ms.topic: article
author: ashishguptaiitb
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
ms.openlocfilehash: 624d91cc7b8518417b45a787f2beae7cb75a7747
ms.sourcegitcommit: 6b4dad9cea8fdad74c493ef62b085dbb9957235d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67486952"
---
# <a name="microsoft-365-app-compliance-program-for-security-compliance-and-privacy-of-third-party-apps"></a>サード パーティ製アプリのセキュリティ用 Microsoft 365 アプリ コンプライアンス プログラム、コンプライアンス、プライバシー

Microsoft コンプライアンス プログラムは、主要な業界標準のフレームワークから派生したコントロールに対してアプリをチェックし、監査します。 プログラムは、顧客データを保護するために強力なセキュリティとコンプライアンスのプラクティスが実施されていることを示します。 プログラムには、次のフェーズがあります。

* 発行元の検証。
* 発行元の構成証明。
* Microsoft 365 認定。

## <a name="publisher-verification"></a>発行元の検証

アプリ開発者がアプリを Microsoft に送信する前に、開発者は検証を受ける必要があります。 開発者は、Microsoft パートナー ネットワーク (MPN) アカウントを使用して ID を確認し、この MPN アカウントをアプリの登録に関連付けます。 発行元の検証は、管理者とエンド ユーザーがアプリケーション開発者の信頼性について理解するのに役立ちます。 発行元の検証には、次のような利点があります。

* 顧客への透明性の強化とリスクの軽減 - この機能は、組織で使用されているどのアプリが信頼できる開発者によって公開されているかを顧客が理解するのに役立ちます。
* ブランドの強化 - Azure Active Directory の同意プロンプト、Enterprise アプリ ページ、エンドユーザーと管理者が使用するその他のユーザー インターフェイスに `verified` バッジが表示されます。
* よりスムーズなエンタープライズ導入 - 管理者は、発行元の検証状態をプライマリ ポリシー条件として、ユーザー同意ポリシーを構成できます。

## <a name="publisher-attestation"></a>発行元の構成証明

発行元による構成証明は、アプリ コンプライアンス プログラムの次の層です。 発行元によって構成証明されたアプリは、アプリのセキュリティとコンプライアンスの対策について管理者に信頼感を与えます。 また、アプリのこの情報を確認する時間を短縮するのにも役立ちます。 構成証明には、[Microsoft Cloud App Security](https://www.microsoft.com/microsoft-365/enterprise-mobility-security/cloud-app-security) によって識別された 80 を超えるリスク要因に対するアプリのセキュリティ、データ処理、コンプライアンス プラクティスが反映されます。 発行元の検証が完了する前に、発行元の構成証明プロセスを開始できます。

アプリ開発者は、アプリのセキュリティとコンプライアンスを評価するために顧客と IT 管理者からよく寄せられる質問を含む自己評価を完了するように求められます。 その後、より簡単でタイムリーな評価のため、Microsoft はこの情報を公開します。 詳細については、「[構成証明ガイド](/microsoft-365-app-certification/docs/enterprise-app-attestation-guide)」を参照してください。

管理者は、3 つの方法で、発行元によって構成証明されたアプリをすばやく確認できます。

* アプリに関する詳細情報を収集する場合、「[Microsoft Teams アプリのセキュリティとコンプライアンス](/microsoft-365-app-certification/teams/teams-apps)」で、特定のアプリのリンクで詳細を確認します。 または、[Teams 管理センター](https://admin.teams.microsoft.com/)で `Publisher attestation` リンクを選択します。

  :::image type="content" source="media/attested-app-tac3.png" alt-text="Teams 管理センターで、発行元による構成証明リンクを選択して、アプリの構成証明の詳細を表示します。":::

* Teams 管理センターで、**[[アプリの管理]](https://admin.teams.microsoft.com/policies/manage-apps)** ページからアプリの詳細を確認する場合、アプリの詳細ページのバナーにある発行元による構成証明済みアイコンを参照してください。

  :::image type="content" source="media/attested-app-tac1.png" alt-text="Teams 管理センターでは、構成証明されたすべてのアプリに発行元による構成証明済みアイコンが表示されます。":::

* Teams 管理センターで[アプリにアクセス許可を付与する](app-permissions-admin-center.md)際の、アプリ名の前の青いチェックマークは、発行元によって構成証明されたアプリか、Microsoft 365 認定されたアプリのどちらかであることを示しています。

   :::image type="content" source="media/attested-app-tac2.png" alt-text="Teams 管理センターの、アクセス許可を付与するダイアログの青いチェックマークは、発行元によって構成証明されたアプリを示しています。":::

構成証明または認定されたアプリの構成証明の詳細ページには、次の詳細が一覧表示されます。

:::image type="content" source="media/attested-app-doc-details.png" alt-text="構成証明されたアプリに関して提供された詳細情報。":::

## <a name="microsoft-365-certification"></a>Microsoft 365 認定

アプリの認定は、次の方法で達成されます。

* 資格のあるアナリストのレビュー。
* アプリのセキュリティとコンプライアンスのフレームワーク、プロセス、および手順を中心とした包括的な評価の承認。

主要な業界標準のフレームワークから派生した一連のセキュリティ コントロールに対してアプリをチェックします。

証明書は、アプリが組織で使用されたときに、顧客データを保護するために強力なセキュリティとコンプライアンスのプラクティスが実施されていることを示します。 管理者とエンドユーザーが証明書でどのような恩恵を受けるかについての詳細は、「[Microsoft 365 アプリ コンプライアンス プログラムの概要](/microsoft-365-app-certification/docs/enterprise-app-certification-guide)」を参照してください。

管理者は、次の方法で Microsoft 365 認定アプリをすばやく確認できます。

* Web 上のアプリに関する詳細情報を収集する場合は、[アプリに関する Microsoft ドキュメント](/microsoft-365-app-certification/teams/teams-apps)のシールド アイコンを参照してください。

  :::image type="content" source="media/attested-app-doc-details.png" alt-text="アプリのセキュリティとコンプライアンスに関する詳細なヘルプ記事で、Microsoft 365 認定情報を確認してください":::

* [Teams 管理センター](https://admin.teams.microsoft.com/policies/manage-apps)でアプリケーションを確認する場合は、[認定] 列を使用してアプリの一覧を並べ替えます。 アイコンを参照し、必要に応じてリンクを選択して、上記のアプリ固有のページにアクセスします。

  :::image type="content" source="media/m365cert-apps-list1.png" alt-text="Teams 管理センターでアプリの Microsoft 365 認定ステータスを表示します。" lightbox="media/m365cert-apps-list2.png":::

* アプリの詳細を表示するときは、アプリ バナーの Microsoft3 65 認定アイコンを参照してください。

  :::image type="content" source="media/m365cert-app-details-banner.png" alt-text="Teams 管理センターで特定のアプリを管理するときに、アプリ バナーで Microsoft 365 認定情報を表示する":::

* Teams 管理センターで[アプリにアクセス許可を付与する](app-permissions-admin-center.md)際の、アプリ名の前の青いチェックマークは、発行元によって構成証明されたアプリか、Microsoft 365 認定されたアプリのどちらかであることを示しています。

   :::image type="content" source="media/attested-app-tac2.png" alt-text="管理者は、アプリが Microsoft 365 認定証明がされていることを確認するため、Teams 管理センターのアクセス許可を付与するダイアログで青いチェックマークをオンにできます":::

## <a name="view-security-compliance-and-privacy-information"></a>セキュリティ、コンプライアンス、プライバシーの情報を表示する

[Microsoft ドキュメント](/microsoft-365-app-certification/teams/teams-apps)と [Teams 管理センター](https://admin.teams.microsoft.com/policies/manage-apps)では、構成証明されたアプリまたは認定済みアプリのセキュリティ、プライバシー、コンプライアンス、および動作に関する情報を確認できます。

### <a name="microsoft-documentation"></a>Microsoft ドキュメント

リストされている各アプリのセキュリティ、プライバシー、コンプライアンスなどの詳細は、「[Microsoft Teams アプリのセキュリティとコンプライアンス](/microsoft-365-app-certification/teams/teams-apps)」からリンクされているアプリ固有のヘルプ記事に記載されています。

:::image type="content" source="media/attested-app-doc-details.png" alt-text="Microsoft コンプライアンス プログラムを受けるアプリに関して提供される詳細情報。":::

### <a name="teams-admin-center"></a>Teams 管理センター

アプリを評価するときは、Microsoft Cloud App Security (MCAS) などの独立した Cloud Access Security Brokers (CASB) を使用して、アプリのセキュリティと動作に関する情報を見つけることができます。 Teams 管理センターには、Microsoft 365 認定アプリの MCAS からのセキュリティとコンプライアンスの情報が含まれています。 アプリの詳細ページでこの情報を確認し、アプリがセキュリティ ニーズを満たしているかどうかを確認します。

> [!NOTE]
> この機能は、組織が MCAS をサポートするライセンスを持っているかどうかにかかわらず、すべての管理者が利用できます。

アプリの MCAS 情報にアクセスするには:

1. Teams 管理センターにサインインし、**Teams アプリ** の **[管理アプリ](https://admin.teams.microsoft.com/policies/manage-apps)** > にアクセスします。

1. **[認定]** を選択してアプリを並べ替え、すべての Microsoft 365 認定アプリをテーブルの一番上にプッシュします。

1. Microsoft 365 認定アプリを選択します。

1. **[セキュリティとコンプライアンス]** タブを選択します。

   :::image type="content" source="media/mcas.png" alt-text="Teams 管理センターの [セキュリティとコンプライアンス] タブを示すスクリーンショット":::

   アプリでサポートされている機能の詳細を取得するには、各カテゴリのドロップダウン リストを選択します。

## <a name="view-privacy-policy-and-terms-of-use-of-an-app"></a>アプリのプライバシー ポリシーと利用規約を表示する

Teams 管理センターの各アプリのページには、アプリのプライバシーに関する声明と利用規約へのリンクが含まれています。

:::image type="content" source="media/tac-app-tou-privacy-info1.png" alt-text="管理者は、Teams 管理センターから、すべてのアプリのプライバシー ポリシーと利用規約へのリンクにアクセスできます。" lightbox="media/tac-app-tou-privacy-info2.png":::

## <a name="related-articles"></a>関連記事

* [アプリのアクセス許可を表示し、管理者の同意を付与します](app-permissions-admin-center.md)。
