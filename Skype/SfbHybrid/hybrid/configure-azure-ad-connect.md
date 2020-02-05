---
title: Azure AD Connect を構成する
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
description: ハイブリッド環境で Azure AD Connect を構成する方法について説明します。
ms.openlocfilehash: 3060ef443fd2ee57157c2590441c5fe04b1d8739
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726937"
---
# <a name="configure-azure-ad-connect-for-teams-and-skype-for-business"></a>Teams と Skype for Business の Azure AD Connect を構成する
 
オンプレミスの Skype for Business Server (または Lync Server) を使用していて、Teams または Skype for Business Online のどちらを使用する予定の組織では、オンプレミスディレクトリと Office 365 を同期するように Azure AD Connect を構成する必要があります。これについては、以下を参照してください。化.  これには、オンプレミスの Skype for Business から Teams に直接移動する組織が含まれます。 特に、Skype for Business オンプレミスを持つ組織では、適切な msRTCSIP 属性を Azure AD に同期させる必要があります。 

> [!NOTE]
> また、既存の Teams ユーザーで Skype for Business オンプレミスも使用している場合は、Skype for Business オンプレミスのアカウントをクラウドに移行する必要があります。これは、Skype for Business ユーザーとの相互運用やフェデレーション組織のユーザーとの通信などの機能をすべて活用するために必要になります。 ユーザーが Teams のみを使用している場合でも、追加機能を提供するために、インフラストラクチャによって当該のオンライン Skype for Business アカウントが要求されます。  この移行を実行するには、ハイブリッドを有効にできるように、Azure AD Connect を正しく構成してください。
 

## <a name="background-information"></a>参考資料

Azure Active Directory Connect は、オンプレミスの Active Directory を常に Office 365 と同期させます。  オンプレミスのディレクトリには、権限のある ID のソースが保持され、オンプレミス環境からの変更は Azure AD に同期されます。 詳細については、「 [AZURE AD Connect Sync](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connect-sync-whatis)」を参照してください。 オンプレミスのすべてのユーザーをクラウドに移行していない場合でも、チーム、Skype for Business オンプレミス、または Skype for Business Online を使用するすべてのユーザーをオンプレミスから Azure AD に同期して、オンプレミスとオンラインのユーザーとの通信を確保する必要があります。 *オンプレミスとオンラインのディレクトリの両方に、組織内のユーザーが表示されます。*


## <a name="configuring-azure-ad-when-you-have-skype-for-business-server"></a>Skype for Business Server を使用している場合の Azure AD の構成 

オンプレミスの Active Directory フォレストが1つでも複数のフォレストであっても、azure ad connect[のトポロジ](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/plan-connect-topologies)で説明するように、Azure ad connect をさまざまなサポートされているトポロジで使用できます。  Skype for Business Server の観点では、主に次の 3 つのバリエーションがあります。 

1. 単一のフォレストで、権限のあるユーザー ID を含み、Skype for Business Server をホストしている。 

2. 複数のフォレストで、そのうち 1 つのフォレストのみが Skype for Business Server をホストしていて、他の 1 つ以上のフォレストが権限のあるユーザー ID を含んでいる (アカウント フォレスト)。 

3. 複数のフォレストで Skype for Business Server を複数配置している。 特定の要件が満たされると、組織はこれらの複数の配置を 1 つの Office 365 テナントに統合できます。

### <a name="single-forest"></a>単一のフォレスト 

ユーザー アカウントと Skype for Business がすべて 1 つのフォレストにホストされている場合は、Azure AD Connect が、当該のフォレストから Azure AD にユーザーが同期されるように構成する必要があります。  Azure AD Connect のインストール ウィザードにはさまざまなオプションがありますが、適切な属性が自動的に Azure Active Directory に同期されます。 お客様は、構成を管理する組み込みの同期ルールやコネクタを変更しないことをお勧めします (インストールウィザードから実行することはできません)。  

### <a name="multiple-forests-with-one-skype-for-business-deployment"></a>複数のフォレストで、1 つの Skype for Business Server を配置 

このシナリオは、通常、リソース フォレスト トポロジと呼ばれます。 ユーザーの権限のある ID が、1 つ以上のアカウント フォレストにホストされています。また、Skype for Business は別のリソース フォレストに配置されています (リソース フォレストには権限のあるユーザー ID もホストされます)。 以下の場合、Skype for Business ユーザーの権限のある ID は、通常、Skype for Business Server と同じフォレストか、または別のフォレストにあります。 

- アカウント フォレストからの権限のある ID を持つユーザーは、リソース フォレスト (Skype for Business Server が配置されているフォレスト) に無効なユーザー オブジェクトとして表示され、リソース フォレストの msRTCSIP-OriginatorSID 属性はアカウント フォレストの SID と一致している。 詳細については[、「Configure a 複数フォレスト環境でのハイブリッド Skype For business の構成](configure-a-multi-forest-environment-for-hybrid.md)」を参照してください。

- Skype for Business Server をホストするリソース フォレストは、アカウント フォレストを信頼している。  

- ID (アカウント フォレストから) と Skype for Business (リソース フォレストから) の両方に関連するユーザー オブジェクトと属性はすべて、Azure AD Connect 経由で正しい値で Azure AD に同期されている。  

 [複数フォレストのオンプレミスシナリオ](configure-a-multi-forest-environment-for-hybrid.md)で、azure ad に適切なオブジェクトと属性の同期を実現するために、Microsoft では、Azure ad Connect を使用して、有効になっているユーザーアカウントと、Skype for business が含まれているフォレストのすべてのフォレストから同期することを強くお勧めします。  すべてのフォレストから同期する場合、当該の ID を統合し、Azure AD に同期するように Azure AD Connect を構成する必要があります。 Azure AD Connect はこのシナリオを処理するように設計されており、その設定のために、ID を結合するアンカーの設定などの組み込みオプションがインストール ウィザードに用意されています。  次のものを選択します。複数のディレクトリにユーザー id が存在します。 --> ObjectSID および msExchangeMasterAccountSID 属性を使用して一致します。


### <a name="multiple-skype-for-business-server-deployments-in-multiple-forests"></a>複数のフォレストでの Skype for Business Server の複数配置 

これは、複数のフォレストで、それぞれのフォレストが Skype for Business Server を含み、1 つの Office 365 テナントがある場合のシナリオです。  Skype for Business Server を含む各フォレストは、AAD Connect を使用して、そのテナントの Azure AD に同期させることができます。 指定した時間に Skype for Business ハイブリッド用に構成できるフォレストは最大でも 1 つだけです。 フォレストでハイブリッドを有効にする前に、他のすべてのフォレストのすべての SIP ドメイン[を無効に](https://docs.microsoft.com/en-us/powershell/module/skype/disable-csonlinesipdomain)する必要があります。 このような環境を Office 365 に統合する方法の詳細については、「 [Teams と Skype for business のクラウド統合](cloud-consolidation.md)」を参照してください。

## <a name="general-requirements"></a>一般的な要件 

Teams と Skype for Business Online の両方のサービスでは、正しい Active Directory 属性が存在し、Azure AD に設定されている必要があります。  Microsoft の一般的な推奨事項は、ユーザー id を含むすべてのフォレストと、Skype for Business Server を含むフォレストを同期することです。

 複数のフォレストにユーザーの ID が存在する場合は、Azure AD Connect で結合を行います。 このガイダンスを実行すると、azure ad connect によって適切な属性が自動的に同期されます。この場合、コネクタまたは同期ルールのいずれかを Azure AD Connect で変更しないことを前提としています。 
  
ユーザー id と Skype for Business Server の展開を含むすべてのフォレストから同期しない場合でも、Teams または Skype を使用しているユーザーに対して、関連性のある id と Skype for business の属性が Azure AD に正しく入力されていることを確認する必要があります。for Business (オンプレミスまたはオンラインの場合)--これを行うには、オンプレミスのディレクトリ同期を追加する必要があります。 詳細については、「 [AZURE AD Connect sync: Attributes が Azure Active Directory に同期](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)されています。」を参照してください。

このようなシナリオでは、Azure AD に属性を設定するための適切な構成を確実に行うことがお客様の責任です。 以下の点にご注意ください。 

- Azure AD に同期するために非標準的な構成を使用すると、誤った構成が発生し、そのためにオンライン ディレクトリのデータが破損する恐れがあります。

- 製品の進化に伴い、Microsoft は、関連するすべてのフォレストが同期される標準的な同期の構成を継続的に確認していきます。 カスタムの同期構成を使用しているお客様は、構成により Azure AD に正しい属性と値が提供されるように、責任をもってご確認ください。 

## <a name="related-information"></a>関連情報

- [ハイブリッド id とは](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/whatis-hybrid-identity?toc=%2Fen-us%2Fazure%2Factive-directory%2Fhybrid%2FTOC.json&bc=%2Fen-us%2Fazure%2Fbread%2Ftoc.json)

- [Azure AD Connect 同期: 同期を理解してカスタマイズする](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/how-to-connect-sync-whatis)

- [Azure AD Connect のトポロジ](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/plan-connect-topologies)

- [Azure AD Connect sync: Azure Active Directory との属性の同期](https://docs.microsoft.com/en-us/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)
