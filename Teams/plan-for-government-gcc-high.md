---
title: Microsoft 365 Government - GCC の高い展開
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: daro
description: 米国政府規制の対象となるデータをOffice 365 の展開をサポートする IT プロ向けガイダンス。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: ced9f5cc68ce18bc7e1670db4031ff85b7c76ff2
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909271"
---
# <a name="plan-for-office-365-government---gcc-high-deployments"></a>Office 365 Government の計画 - GCC の高い展開

このガイダンスは、Office 365 Government – GCC High の使用がこれらの要件を満たすために適切である、米国連邦政府機関のエンティティまたは政府の規制の対象となるデータを処理するその他のエンティティで Office 365 の展開を推進している IT プロを対象とします。

> [!NOTE]
> お客様の組織が既に Office 365 Government – GCC High eligibility requirements を満たし、プログラムに適用され、プログラムに同意されている場合は、手順 1 と 2 をスキップして、手順 3 に直接進みます。

## <a name="step-1-determine-whether-your-organization-needs-office-365-government---gcc-high-and-meets-eligibility-requirements"></a>手順 1. 組織で 365 Government - GCC High をOffice、資格要件を満たしていることを確認します。 

Office 365 Government - GCC High 環境は、クラウド サービスに関する米国政府の要件に準拠します。 Office 365 の機能を利用できるだけでなく、組織は Office 365 Government – GCC High 固有の次の機能を利用できます。

- 組織の顧客コンテンツは、企業や 365 サービスの顧客コンテンツから論理的に分離され、Office 365 サービスから分離されます。
- 組織の顧客コンテンツは米国内に保存されます。
- 組織の顧客コンテンツへのアクセスは、Microsoft の担当者に限定されます。
- Office 365 Government – GCC High は、米国の公共機関のお客様に必要な認定と認定に準拠しています。

米国政府機関向け Office 365 Government – GCC High サービスの詳細については、Office [365 Government](https://products.office.com/government/compare-office-365-government-plans)プラン (利用資格要件を含む) を参照[してください。](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)

Office [365 US Government](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) サービスの説明では、米国内のコンプライアンス要件を満たしていることを中心にしたプラットフォームの利点について説明します。


> [!Tip]
> サービスの説明の情報テーブルを Excel ブックに転送し、組織 **の Y/N** に関連し、組織の **Y/N** のニーズを満たすという 2 つの列を追加することができます。 その後、このリストを同僚と確認して、このサービスが組織のニーズを満たしたと確認できます。


|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>365 Government - GCC High Office組織に適したシステムかどうかを決定します。</li><li>組織が資格要件を満たしていることを確認します。</li></ul> |

> [!Note]
> Office 365 Government - GCC High は、米国でのみご利用いただけます。 米国政府機関以外のお客様は [、365 政府機関向けプランOffice選択できます](https://products.office.com/en/government/compare-office-365-government-plans)。

## <a name="step-2-apply-for-office-365-government---gcc-high"></a>手順 2. Office 365 Government - GCC High に申請する

このサービスが組織に合っている場合は、このサービスを申請する [プロセスを開始します](https://products.office.com/government/eligibility-validation)。


## <a name="step-3-understand-office-365-government---gcc-high-default-security-settings"></a>手順 3. 365 government Office GCC の既定のセキュリティ設定について説明します。

管理者とセキュリティ設定を変更する前に慎重[](enable-features-office-365.md)に確認し、既定のセキュリティ設定を変更する前にコンプライアンスへの影響を検討することをお勧めします。

|    |     |
|-----------|------------|
| ![判断ポイントを表すアイコン](media/audio_conferencing_image7.png) <br/>判断ポイント|<ul><li>既定の Office 365 Government - GCC High Security 設定を変更する必要があるかどうかを決定し、最初に変更の影響を理解します。</li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-office-365-government---gcc-high"></a>手順 4. Office 365 Government - GCC High で現在使用できる Teams の機能を理解する

政府機関向けクラウドのお客様の要件に対応するために、Office 365 Government の Teams とエンタープライズ プランの GCC High と Teams にはいくつかの違いがあります。 使用できる機能を確認するには、次の表を参照してください。

[Microsoft Teams サービスの説明](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

## <a name="step-5-plan-for-governance"></a>手順 5. ガバナンスの計画

ガバナンスの要件と、ガバナンスを満たす方法を決定します。 詳細については [、「Teams のガバナンスの計画」](plan-teams-governance.md) を参照してください。

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/>|判断ポイント |<ul><li>Teams のガバナンス計画のガイドラインに従って、ガバナンス要件を決定 [して文書化します](plan-teams-governance.md)。 </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a>手順 6. 共同作業のために Teams を展開する

Office 365 Government – GCC High にオンボードされた後、Microsoft Teams の展開方法で説明されている推奨される展開パス [に従います](How-to-roll-out-teams.md)。 導入および変更管理チームと Teams のチャンピオンと必ず関与してください。

また、FastTrack または選択 [したパートナー](https://www.microsoft.com/fasttrack) と一緒にサービスをオンボードできます。

> [!NOTE]
> GCCH 環境用の Mac Teams クライアントはまだサポートされていません。

