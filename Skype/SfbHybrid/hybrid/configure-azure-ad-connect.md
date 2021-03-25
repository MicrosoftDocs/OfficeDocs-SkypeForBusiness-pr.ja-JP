---
title: Azure AD接続を構成する
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
description: ハイブリッド環境で Azure AD Connect を構成する手順。
ms.openlocfilehash: 5095f3b22dfe3f4dcbfd2a0e3296794b80433b82
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119016"
---
# <a name="configure-azure-ad-connect-for-teams-and-skype-for-business"></a>Teams と Skype for Business の Azure AD Connect を構成する
 
Skype for Business Server (または Lync Server) をオンプレミスに持ち、Teams または Skype for Business Online のいずれかを使用する予定の組織は、このドキュメントで説明するように、オンプレミス ディレクトリを Microsoft 365 または Office 365 と同期するように Azure AD Connect を構成する必要があります。  これには、Skype for Business オンプレミスから Teams に直接移動する組織が含まれます。 特に、Skype for Business オンプレミスを持つ組織では、適切な msRTCSIP 属性を Azure AD に同期させる必要があります。 

> [!NOTE]
> また、既存の Teams ユーザーで Skype for Business オンプレミスも使用している場合は、Skype for Business オンプレミスのアカウントをクラウドに移行する必要があります。これは、Skype for Business ユーザーとの相互運用やフェデレーション組織のユーザーとの通信などの機能をすべて活用するために必要になります。 ユーザーが Teams のみを使用している場合でも、追加機能を提供するために、インフラストラクチャによって当該のオンライン Skype for Business アカウントが要求されます。  この移行を実行するには、ハイブリッドを有効にできるように、Azure AD Connect を正しく構成してください。
 

## <a name="background-information"></a>参考資料

Azure Active Directory Connect は、オンプレミスの Active Directory を Microsoft 365 または microsoft 365 または Office 365 と継続的に同期します。  オンプレミスのディレクトリには、権限のある ID のソースが保持され、オンプレミス環境からの変更は Azure AD に同期されます。 詳細については [、「Azure AD Connect Sync」を参照してください](/azure/active-directory/hybrid/how-to-connect-sync-whatis)。 すべてのユーザーをオンプレミスからクラウドに移行していない場合でも、オンプレミスユーザーとオンライン ユーザー間の通信を確保するために、Teams、Skype for Business オンプレミス、または Skype for Business Online を使用するすべてのユーザーをオンプレミスから Azure AD に同期する必要があります。 *オンプレミスとオンラインのディレクトリの両方に、組織内のユーザーが表示されます。*


## <a name="configuring-azure-ad-when-you-have-skype-for-business-server"></a>Skype for Business Server を使用している場合の Azure AD の構成 

オンプレミスの Active Directory フォレストが 1 つでも複数のフォレストでも、Azure AD Connect は、「トポロジ for Azure AD Connect」で説明されているさまざまなサポート [されるトポロジで使用できます](/azure/active-directory/hybrid/plan-connect-topologies)。  Skype for Business Server の観点では、主に次の 3 つのバリエーションがあります。 

1. 単一のフォレストで、権限のあるユーザー ID を含み、Skype for Business Server をホストしている。 

2. 複数のフォレストで、そのうち 1 つのフォレストのみが Skype for Business Server をホストしていて、他の 1 つ以上のフォレストが権限のあるユーザー ID を含んでいる (アカウント フォレスト)。 

3. 複数のフォレストで Skype for Business Server を複数配置している。 特定の要件が満たされている場合、組織は、これらの複数の展開を単一の Microsoft 365 または 365 組織Office統合できます。

### <a name="single-forest"></a>単一のフォレスト 

ユーザー アカウントと Skype for Business がすべて 1 つのフォレストにホストされている場合は、Azure AD Connect が、当該のフォレストから Azure AD にユーザーが同期されるように構成する必要があります。  Azure AD Connect のインストール ウィザードにはさまざまなオプションがありますが、適切な属性が自動的に Azure Active Directory に同期されます。 構成を管理する組み込みの同期ルールやコネクタ (インストール ウィザードでは使用できない) を変更する必要があります。  

### <a name="multiple-forests-with-one-skype-for-business-deployment"></a>複数のフォレストで、1 つの Skype for Business Server を配置 

このシナリオは、通常、リソース フォレスト トポロジと呼ばれます。 ユーザーの権限のある ID が、1 つ以上のアカウント フォレストにホストされています。また、Skype for Business は別のリソース フォレストに配置されています (リソース フォレストには権限のあるユーザー ID もホストされます)。 以下の場合、Skype for Business ユーザーの権限のある ID は、通常、Skype for Business Server と同じフォレストか、または別のフォレストにあります。 

- アカウント フォレストからの権限のある ID を持つユーザーは、リソース フォレスト (Skype for Business Server が配置されているフォレスト) に無効なユーザー オブジェクトとして表示され、リソース フォレストの msRTCSIP-OriginatorSID 属性はアカウント フォレストの SID と一致している。 詳細については [、「Configure a multi-forest environment for hybrid Skype for Business」を参照してください](configure-a-multi-forest-environment-for-hybrid.md)。

- Skype for Business Server をホストするリソース フォレストは、アカウント フォレストを信頼している。  

- ID (アカウント フォレストから) と Skype for Business (リソース フォレストから) の両方に関連するユーザー オブジェクトと属性はすべて、Azure AD Connect 経由で正しい値で Azure AD に同期されている。  

 複数フォレストのオンプレミス シナリオで Azure AD への適切な[](configure-a-multi-forest-environment-for-hybrid.md)オブジェクトと属性の同期を実現するために、Microsoft は Azure AD Connect を使用して、ユーザー アカウントを有効にしているすべてのフォレストと Skype for Business を含むフォレストから同期を強く推奨します。  すべてのフォレストから同期する場合、当該の ID を統合し、Azure AD に同期するように Azure AD Connect を構成する必要があります。 Azure AD Connect はこのシナリオを処理するように設計されており、その設定のために、ID を結合するアンカーの設定などの組み込みオプションがインストール ウィザードに用意されています。  [ユーザー ID が複数のディレクトリに存在する] を選択します。 ObjectSID 属性と msExchangeMasterAccountSID 属性>を使用して一致します。


### <a name="multiple-skype-for-business-server-deployments-in-multiple-forests"></a>複数のフォレストでの Skype for Business Server の複数配置 

このシナリオでは、Skype for Business Server を含む複数のフォレストと、1 つの Microsoft 365 組織または 365 組織Officeがあります。  Skype for Business Server を含む各フォレストは、AAD Connect を使用してAD組織の Azure ADに同期できます。 指定した時間に Skype for Business ハイブリッド用に構成できるフォレストは最大でも 1 つだけです。 フォレストでハイブリッドを有効にする前に [、disable-csonlineSipDomain](/powershell/module/skype/disable-csonlinesipdomain)を使用して、他のすべてのフォレストのすべての SIP ドメインを無効にする必要があります。 このような環境を Microsoft 365 または Office 365 に統合する方法の詳細については、「Teams と Skype for Business のクラウド統合」 [を参照してください](cloud-consolidation.md)。

## <a name="general-requirements"></a>一般的な要件 

Teams サービスと Skype for Business Online サービスの両方で、正しい Active Directory 属性が存在し、Azure AD に設定されている必要があります。  Microsoft の一般的な推奨事項は、ユーザー ID を含むすべてのフォレストと、Skype for Business Server を含むフォレストを同期する方法です。

 複数のフォレストにユーザーの ID が存在する場合は、Azure AD Connect で結合を行います。 このガイダンスに従った場合、Azure AD Connect は、Azure AD Connect のコネクタまたは同期ルールを変更しない場合、正しい属性を自動的に同期します。 
  
ユーザー ID と Skype for Business Server 展開を含むすべてのフォレストから同期しない場合でも、Teams または Skype for Business を使用するすべてのユーザー (オンプレミスまたはオンライン) を使用するすべてのユーザーに対して、関連する ID と Skype for Business 属性が Azure AD に正しく設定されていることを確認する必要があります。これは、オンプレミスディレクトリの同期が必要な可能性があります。 詳細については [、「Azure AD接続同期: Azure Active Directory に同期された属性」を参照してください](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)。

このようなシナリオでは、Azure サーバーに属性を設定するための適切な構成を確実に行うのは、お客様のAD。 以下の点にご注意ください。 

- Azure AD に同期するために非標準的な構成を使用すると、誤った構成が発生し、そのためにオンライン ディレクトリのデータが破損する恐れがあります。

- 製品の進化に伴い、Microsoft は、関連するすべてのフォレストが同期される標準的な同期の構成を継続的に確認していきます。 カスタムの同期構成を使用しているお客様は、構成により Azure AD に正しい属性と値が提供されるように、責任をもってご確認ください。 

## <a name="related-information"></a>関連情報

- [ハイブリッド ID とは](/azure/active-directory/hybrid/whatis-hybrid-identity)

- [Azure AD接続の同期: 同期の理解とカスタマイズ](/azure/active-directory/hybrid/how-to-connect-sync-whatis)

- [Azure AD Connect のトポロジ](/azure/active-directory/hybrid/plan-connect-topologies)

- [Azure AD接続の同期: Azure Active Directory に同期された属性](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)