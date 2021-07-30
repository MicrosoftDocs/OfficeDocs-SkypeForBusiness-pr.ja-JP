---
title: Azure の構成AD Connect
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: ハイブリッド環境で Azure AD Connect構成する手順。
ms.openlocfilehash: 208d44a9bb8db909d5d562b23cbcfeada41318a7
ms.sourcegitcommit: d0fb9035903d9e1ce184417250913db10608b1a9
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/29/2021
ms.locfileid: "53660685"
---
# <a name="configure-azure-ad-connect-for-teams-and-skype-for-business"></a>Teams と Skype for Business の Azure AD Connect を構成する

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

 
Skype for Business Server (または Lync Server) をオンプレミスに持ち、Teams を使用する予定の組織は、オンプレミス ディレクトリと Microsoft 365 を同期するように Azure AD Connect を構成する必要があります。 この要件には、オンプレミスからオンプレミスに直接Skype for Business組織が含Teams。 オンプレミスにSkype for Business組織では、適切な msRTCSIP 属性が Azure AD に同期されている必要があります。

> [!NOTE]
> Skype for Business オンプレミスを持つ既存の Teams ユーザーは、Skype for Business ユーザーとの相互運用やフェデレーション組織のユーザーとの通信など、完全な機能を取得するために、Skype for Business オンプレミス アカウントをクラウドに移動する必要があります。 ユーザーが Teams のみを使用している場合でも、追加機能を提供するために、インフラストラクチャによって当該のオンライン Skype for Business アカウントが要求されます。 この移行を実行するには、ハイブリッドを有効にできるように、Azure AD Connect を正しく構成してください。
 

## <a name="background-information"></a>背景情報

Azure Active Directory Connectオンプレミスの Active Directory と継続的に同期を維持Microsoft 365。 オンプレミスのディレクトリには、権限のある ID のソースが保持され、オンプレミス環境からの変更は Azure AD に同期されます。 詳細については[、「Azure AD Connect Sync」を参照してください](/azure/active-directory/hybrid/how-to-connect-sync-whatis)。  

すべてのユーザーをオンプレミスからクラウドに移行しない場合は、Teams または Skype for Business オンプレミスを使用するすべてのユーザーをオンプレミスから Azure AD に同期して、オンプレミスユーザーとオンライン ユーザー間の通信を確保する必要があります。 *オンプレミスとオンラインのディレクトリの両方に、組織内のユーザーが表示されます。*


## <a name="configuring-azure-ad-when-you-have-skype-for-business-server"></a>Skype for Business Server を使用している場合の Azure AD の構成 

オンプレミスの Active Directory フォレストが 1 つでも複数のフォレストでも、Azure AD Connect は、「トポロジ for Azure AD Connect」で説明したように、さまざまなサポートされているトポロジ[で使用できます](/azure/active-directory/hybrid/plan-connect-topologies)。 この方法の観点Skype for Business Server、次の 3 つのバリエーションがあります。 

1. 単一のフォレストで、権限のあるユーザー ID を含み、Skype for Business Server をホストしている。 

2. 複数のフォレストで、そのうち 1 つのフォレストのみが Skype for Business Server をホストしていて、他の 1 つ以上のフォレストが権限のあるユーザー ID を含んでいる (アカウント フォレスト)。 

3. 複数のフォレストで Skype for Business Server を複数配置している。 特定の要件が満たされている場合、組織は、これらの複数の展開を 1 つの組織に統合Microsoft 365できます。

### <a name="single-forest"></a>単一のフォレスト 

ユーザー アカウントと Skype for Business がすべて 1 つのフォレストにホストされている場合は、Azure AD Connect が、当該のフォレストから Azure AD にユーザーが同期されるように構成する必要があります。  Azure AD Connect のインストール ウィザードにはさまざまなオプションがありますが、適切な属性が自動的に Azure Active Directory に同期されます。 構成を管理する組み込みの同期ルールやコネクタ (インストール ウィザードでは使用できない) を変更する必要があります。  

### <a name="multiple-forests-with-one-skype-for-business-deployment"></a>複数のフォレストで、1 つの Skype for Business Server を配置 

このシナリオは、通常、リソース フォレスト トポロジと呼ばれます。 ユーザーの権限のある ID が、1 つ以上のアカウント フォレストにホストされています。また、Skype for Business は別のリソース フォレストに配置されています (リソース フォレストには権限のあるユーザー ID もホストされます)。 以下の場合、Skype for Business ユーザーの権限のある ID は、通常、Skype for Business Server と同じフォレストか、または別のフォレストにあります。 

- アカウント フォレストの権限のある ID を持つユーザーは、リソース フォレスト (Skype for Business Serverが展開されている) で無効なユーザー オブジェクトとして表されます。 リソース フォレストの msRTCSIP-OriginatorSID 属性は、アカウント フォレストの SID と一致している必要があります。 詳細については[、「Configure a multi-forest environment for hybrid Skype for Business」 を参照してください](configure-a-multi-forest-environment-for-hybrid.md)。

- Skype for Business Server をホストするリソース フォレストは、アカウント フォレストを信頼している。  

- ID (アカウント フォレストから) と Skype for Business (リソース フォレストから) の両方に関連するすべてのユーザー オブジェクトと属性は、Azure AD に同期され、Azure AD Connect を通じて正しい値が使用されます。  

  複数フォレストのオンプレミス シナリオで Azure AD に適切な[](configure-a-multi-forest-environment-for-hybrid.md)オブジェクトと属性の同期を実現するには、Azure AD Connect を使用して、ユーザー アカウントを有効にしているすべてのフォレストと、Skype for Business を含むフォレストから同期を行うのを強く推奨します。 すべてのフォレストから同期する場合、当該の ID を統合し、Azure AD に同期するように Azure AD Connect を構成する必要があります。 Azure AD Connect はこのシナリオを処理するように設計されており、その設定のために、ID を結合するアンカーの設定などの組み込みオプションがインストール ウィザードに用意されています。 複数のディレクトリにユーザー **ID** が存在し、--> ObjectSID 属性と **msExchangeMasterAccountSID** 属性を使用して一致します。


### <a name="multiple-skype-for-business-server-deployments-in-multiple-forests"></a>複数のフォレストでの Skype for Business Server の複数配置 

このシナリオでは、複数のフォレストが含まれるSkype for Business Server、1 つのフォレストMicrosoft 365があります。 このリソースを含Skype for Business Server各フォレストは、AAD ADを使用して、その組織の Azure Connect。 指定した時間に Skype for Business ハイブリッド用に構成できるフォレストは最大でも 1 つだけです。 フォレストでハイブリッドを有効にする前に [、disable-csonlineSipDomain](/powershell/module/skype/disable-csonlinesipdomain)を使用して、他のすべてのフォレストのすべての SIP ドメインを無効にする必要があります。 詳細については、「クラウド統合[for Teams」をSkype for Business。](cloud-consolidation.md)

## <a name="general-requirements"></a>一般的な要件 

このTeamsは、正しい Active Directory 属性が存在し、Azure サーバーに設定されている必要AD。 Microsoft では、ユーザー ID を含むすべてのフォレストと、ユーザー ID を含むフォレストを同期Skype for Business Server。

 複数のフォレストにユーザーの ID が存在する場合は、Azure AD Connect で結合を行います。 このガイダンスに従うと、Azure AD Connect のコネクタまたは同期規則を変更していなければ、Azure AD Connect により、自動的に正しい属性が同期されます。 
  
ユーザー ID と Skype for Business Server 展開を含むすべてのフォレストから同期しない場合は、Teams または Skype for Business を使用するすべてのユーザー (オンプレミスまたはオンライン) に関連する ID と Skype for Business 属性が Azure AD に正しく設定されていることを確認する必要があります。 これにより、オンプレミスディレクトリの同期が追加で必要になります。 詳細については[、「Azure AD Connect同期: 同期された属性」をAzure Active Directory。](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)

このようなシナリオでは、Azure サーバーに属性を設定するための適切な構成を確実に行うのは、お客様のAD。 以下の点にご注意ください。 

- Azure AD に同期するために非標準的な構成を使用すると、誤った構成が発生し、そのためにオンライン ディレクトリのデータが破損する恐れがあります。

- 製品の進化に伴い、Microsoft は、関連するすべてのフォレストが同期される標準的な同期の構成を継続的に確認していきます。 カスタムの同期構成を使用しているお客様は、構成により Azure AD に正しい属性と値が提供されるように、責任をもってご確認ください。 

## <a name="related-information"></a>関連情報

- [ハイブリッド ID とは](/azure/active-directory/hybrid/whatis-hybrid-identity)

- [Azure AD Connect同期: 同期の理解とカスタマイズ](/azure/active-directory/hybrid/how-to-connect-sync-whatis)

- [Azure AD Connect のトポロジ](/azure/active-directory/hybrid/plan-connect-topologies)

- [Azure AD Connect同期: 同期された属性Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)