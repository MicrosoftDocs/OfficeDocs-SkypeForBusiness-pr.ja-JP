---
title: Azure AD Connect を構成する
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: ハイブリッド環境で Azure AD Connect を構成する方法について説明します。
ms.openlocfilehash: 9df0e42224d3186c3d7b5b1748412e9ec9121897
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "36160645"
---
# <a name="configure-azure-ad-connect-for-teams-and-skype-for-business"></a>Teams および Skype for Business 用に Azure AD Connect を構成する
 
オンプレミスの Skype for Business Server (または Lync Server) を使用していて、Teams または Skype for Business Online のどちらを使用する予定の組織では、オンプレミスディレクトリと Office 365 を同期するように Azure AD Connect を構成する必要があります。これについては、以下を参照してください。化.  これには、オンプレミスの Skype for Business から Teams に直接移動する組織が含まれます。 特に、オンプレミスの Skype for Business を使用している組織では、適切な msRTCSIP 属性が確実に Azure AD に同期されている必要があります。 

> [!NOTE]
> 既存の Teams skype for business のオンプレミスを持つユーザーも、skype for business のオンプレミスのアカウントをクラウドに移動して、skype for business ユーザーとの相互運用を可能にするために、クラウドに移行する必要があります。フェデレーション組織のユーザーと通信します。 ユーザーが Teams のみを使用する場合でも、追加機能を提供するために、このオンライン Skype for Business アカウントがインフラストラクチャによって必要になります。  この移行を行うには、ハイブリッドを有効にできるように、Azure AD Connect が正しく構成されていることを確認する必要があります。
 

## <a name="background-information"></a>参考資料

Azure Active Directory Connect は、オンプレミスの Active Directory を常に Office 365 と同期させます。  オンプレミスのディレクトリは id の権限のあるソースのままで、オンプレミス環境からの変更は Azure AD に同期されます。 詳細については、「 [AZURE AD Connect Sync](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connect-sync-whatis)」を参照してください。 オンプレミスのすべてのユーザーをクラウドに移行していない場合でも、Teams、Skype for Business オンプレミス、または Skype for Business Online を使用するすべてのユーザーをオンプレミスから Azure AD に同期して、オンプレミスとオンラインのユーザーとの通信を確保する必要があります。. *組織内のユーザーは、オンプレミスとオンラインの両方のディレクトリに表示されます。*


## <a name="configuring-azure-ad-when-you-have-skype-for-business-server"></a>Skype for Business Server を使用している場合の Azure AD の構成 

オンプレミスの Active Directory フォレストが1つでも複数のフォレストであっても、azure ad connect[のトポロジ](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/plan-connect-topologies)で説明するように、Azure ad connect をさまざまなサポートされているトポロジで使用できます。  Skype for Business Server の観点から見ると、主に次の3つのバリエーションがあります。 

1. 権限のあるユーザー id を含み、Skype for Business Server をホストする単一のフォレスト。 

2. 複数のフォレスト: Skype for Business Server をホストする1つのフォレスト、および権限のあるユーザー id (アカウントフォレスト) を含む1つ以上の他のフォレスト。 

3. 複数のフォレストにある Skype for Business Server の複数の展開。 特定の要件が満たされている場合、組織はこれらの複数の展開を1つの Office 365 テナントに統合することができます。

### <a name="single-forest"></a>単一のフォレスト 

ユーザーアカウントと Skype for Business がすべて単一のフォレストにホストされている場合は、Azure AD Connect がこのフォレストのユーザーを Azure AD に同期するように構成されていることを確認する必要があります。  Azure AD 接続インストールウィザードにはさまざまなオプションがありますが、適切な属性が自動的に Azure Active Directory に同期されます。 お客様は、構成を管理する組み込みの同期ルールやコネクタを変更しないことをお勧めします (インストールウィザードから実行することはできません)。  

### <a name="multiple-forests-with-one-skype-for-business-deployment"></a>1つの Skype for Business 展開を備えた複数のフォレスト 

このシナリオは、多くの場合、リソースフォレストのトポロジと呼ばれます。 ユーザーの権限のある id は1つ以上のアカウントフォレストでホストされ、Skype for Business は個別のリソースフォレストに展開されます (それ自体も権限のあるユーザー id をホストする場合があります)。 一般に、Skype for Business ユーザーの権限 id は、次のように指定された Skype for Business Server または別のフォレストの同じフォレストに存在することができます。 

- アカウントフォレストから権限のある id を持つユーザーは、リソースフォレスト (Skype for Business Server が展開されている) で無効なユーザーオブジェクトとして表され、リソースフォレスト内の msRTCSIP-are Atorsid 属性は、アカウントフォレスト。 詳細については[、「Configure a 複数フォレスト環境でのハイブリッド Skype For business の構成](configure-a-multi-forest-environment-for-hybrid.md)」を参照してください。

- Skype for Business Server をホストしているリソースフォレストは、アカウントフォレストを信頼しています。  

- Id (アカウントフォレストから) および Skype for Business (リソースフォレストから) の両方の関連するすべてのユーザーオブジェクトと属性は、azure AD Connect を介して正しい値を持つ Azure AD に同期されます。  

 [複数フォレストのオンプレミスのシナリオ](configure-a-multi-forest-environment-for-hybrid.md)で、azure ad に適切なオブジェクトおよび属性の同期を実現するために、Microsoft では、Azure ad Connect を使用して、有効になっているユーザーアカウントとフォレストを持つすべてのフォレストから同期することを強くお勧めします。Skype for Business が含まれています。  すべてのフォレストから同期する場合は、これらの id をマージして Azure AD に同期するように Azure AD Connect を構成する必要があります。 Azure AD Connect はこのシナリオを処理するように設計されており、これを設定するためにインストールウィザードに組み込みのオプションが用意されています。これは、id への参加のためのアンカーの設定を含みます。  次のものを選択します。複数のディレクトリにユーザー id が存在します。 --> ObjectSID および msExchangeMasterAccountSID 属性を使用して一致します。


### <a name="multiple-skype-for-business-server-deployments-in-multiple-forests"></a>複数のフォレストでの複数の Skype for Business Server の展開 

このシナリオでは、複数のフォレストがあり、それぞれに Skype for Business サーバーと1つの Office 365 テナントが含まれています。  Skype for Business Server を含む各フォレストは、AAD Connect を使用して、そのテナントの Azure AD に同期させることができます。 多くの場合、特定の時点で Skype for Business ハイブリッドに対して構成できるフォレストは1つだけです。 フォレストでハイブリッドを有効にする前に、他のすべてのフォレストのすべての[](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain)SIP ドメインを無効にする必要があります。 このような環境を Office 365 に統合する方法の詳細については、「 [Teams と Skype for business のクラウド統合](cloud-consolidation.md)」を参照してください。

## <a name="general-requirements"></a>一般的な要件 

Teams と Skype for Business Online の両方のサービスでは、正しい Active Directory 属性が存在し、Azure AD に設定されている必要があります。  Microsoft の一般的な推奨事項は、ユーザー id を含むすべてのフォレストと、Skype for Business Server を含むフォレストを同期することです。

 複数のフォレストにわたってユーザーの id が存在する場合、Azure AD Connect はマージを実行する必要があります。 このガイダンスを実行すると、azure ad connect によって適切な属性が自動的に同期されます。この場合、コネクタまたは同期ルールのいずれかを Azure AD Connect で変更しないことを前提としています。 
  
ユーザー id と Skype for Business Server の展開を含むすべてのフォレストから同期しない場合でも、Teams または Skype を使用しているユーザーに対して、関連性のある id と Skype for business の属性が Azure AD に正しく入力されていることを確認する必要があります。for Business (オンプレミスまたはオンラインの場合)--これを行うには、オンプレミスのディレクトリ同期を追加する必要があります。 詳細については、「 [AZURE AD Connect sync: Attributes が Azure Active Directory に同期](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)されています。」を参照してください。

このようなシナリオでは、Azure AD に属性を設定するための適切な構成を確実に行うことがお客様の責任です。 以下の点にご注意ください。 

- 非標準の構成を使用して Azure AD に同期すると、誤った構成が発生し、オンラインディレクトリ内でデータが破損する可能性があるため、リスクがありません。

- 製品が進化するにつれて、Microsoft は、すべての関連するフォレストが同期される標準的な同期構成の検証を続行します。 カスタム同期構成を使用しているお客様は、構成によって適切な属性と値が Azure AD に確実に配信されるようにする必要があります。 

## <a name="related-information"></a>関連情報

- [ハイブリッド id とは](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/whatis-hybrid-identity?toc=%2Fen-us%2Fazure%2Factive-directory%2Fhybrid%2FTOC.json&bc=%2Fen-us%2Fazure%2Fbread%2Ftoc.json)

- [Azure AD Connect 同期: 同期を理解してカスタマイズする](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connect-sync-whatis)

- [Azure AD Connect のトポロジ](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/plan-connect-topologies)

- [Azure AD Connect sync: Azure Active Directory との属性の同期](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)
