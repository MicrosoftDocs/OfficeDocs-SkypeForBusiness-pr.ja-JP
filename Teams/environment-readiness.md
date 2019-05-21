---
title: Microsoft Teams の導入に向けた環境の準備を確認する
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 5/11/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dansteve
description: Microsoft Teams の導入に向けた環境の準備の確認事項について説明します。
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1794b87beb1c6b1f1e499c214cde8d3e0b9b0a34
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32235406"
---
<a name="check-your-environments-readiness-for-microsoft-teams"></a>Microsoft Teams の導入に向けた環境の準備を確認する
===========================================

クラウドへの移行作業は各組織によって異なり、現在の状況が Teams がどのように機能するかに大きな影響を与えます。

教育機関は、Microsoft Teams を展開する前に[School Data Sync を展開](https://docs.microsoft.com/schooldatasync/)することを強くお勧めします。 School Data Sync は、学校の SIS リストデータを使用して、Microsoft Teams および他のアプリケーションのクラスとグループを自動的に作成します。

チームで最高のエクスペリエンスを得るためには、組織が Exchange Online と SharePoint Online を展開している必要があります。 また、現在の環境が Teams に対応していることを確認する必要があります。  ヘルプについては、次のリンクを参照してください。

-   組織で Office 365 ワークロードのいずれも展開していない場合は、「[一般法人向け Office 365 を使い始める](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)」をご覧ください。

-   組織で Office 365 の確認済みドメインを追加または構成していない場合は、「[Office 365 ドメインを確認して、所有権や、非営利団体または教育機関のステータスを証明する、または Yammer のアクティブ化を行う](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)」をご覧ください。

-   組織で識別情報を Azure Active Directory と同期していない場合は、「[Microsoft Teams での ID モデルと認証](identify-models-authentication.md)」をご覧ください。

-   組織で Exchange Online が導入されていない場合は、「[Exchange と Microsoft Teams の連携](Exchange-Teams-interact.md)」をご覧ください。

-   組織で SharePoint Online が導入されていない場合は、「[Microsoft Teams との SharePoint Online と OneDrive for Business の連携](SharePoint-OneDrive-interact.md)」をご覧ください。

- 組織が教育機関であり、学生情報システム (SIS) を使用している場合は、Microsoft Teams を展開する前に[School Data Sync を展開](https://docs.microsoft.com/schooldatasync/)してください。

- 組織に既存のオンプレミス Skype for Business Server (または Lync Server) の展開がある場合は、オンプレミスのディレクトリを Office 365 と同期するように Azure AD Connect を構成する必要があります。  詳細については、「 [Teams および Skype For business 用に AZURE AD Connect を構成する](https://docs.microsoft.com/en-us/skypeforbusiness/hybrid/configure-azure-ad-connect)」を参照してください。