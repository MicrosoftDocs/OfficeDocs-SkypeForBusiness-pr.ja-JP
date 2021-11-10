---
title: 構成Azure AD Connect
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
search.appverid: MET150
description: ハイブリッド環境でAzure AD Connect構成する手順。
ms.openlocfilehash: cfb290ecc6892001a9e20d9260c54c076a51dfe3
ms.sourcegitcommit: 11a803d569a57410e7e648f53b28df80a53337b6
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/10/2021
ms.locfileid: "60887215"
---
# <a name="configure-azure-ad-connect-for-teams-and-skype-for-business"></a>Teams と Skype for Business の Azure AD Connect を構成する

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

 
Teamsを使用するには、Skype for Business Server または Lync Server 2013 のオンプレミス展開を持つ組織は、Azure AD Connect を構成して、オンプレミス ディレクトリを Microsoft 365 と同期させる必要があります。 オンプレミスにSkype for Business Server組織では、適切な msRTCSIP 属性が適切な msRTCSIP 属性と同期Azure AD。 この記事では、"Skype for Business Server" への参照は Lync Server 2013 にも適用されます。

> [!NOTE]
> - 完全な機能を取得するには、Teams オンプレミスの Skype for Business を持つ既存のユーザーが、Skype for Business オンプレミス アカウントをクラウドに移動する必要があります。 たとえば、ユーザーとユーザーを相互運用する機能や、Skype for Business組織のユーザーとの通信などの機能を取得します。 オンプレミスのユーザーが Teams のみを使用する場合は、TeamsOnly ユーザーとして完全な Teams 機能を提供するために、ユーザーをクラウドに移動する必要があります。 この移行を行う場合は、ハイブリッドを有効Azure AD Connect構成する必要があります。
> - すぐにオンプレミスからクラウドにユーザーを移動する予定がない場合は、Teams アカウントと Skype for Business Server アカウントが共に存在するAzure AD Connect を構成する必要があります。
 

## <a name="background-information"></a>背景情報

Azure Active Directory Connectオンプレミスの Active Directory と継続的に同期を維持Microsoft 365。 オンプレミス のディレクトリは、権限を持つ ID のソースのままですが、オンプレミス環境からの変更は、オンプレミス環境から Azure AD。 詳細については、「同期」[をAzure AD Connectしてください](/azure/active-directory/hybrid/how-to-connect-sync-whatis)。 *組織内のユーザーは、オンプレミスディレクトリとオンライン ディレクトリの両方で表されます。*  これらのアカウントの共存をTeams、またはSkype for Businessを使用するユーザーは、オンプレミスからAzure ADに同期する必要があります。 さらに、ハイブリッド接続を介してオンプレミスユーザーとオンライン ユーザー間の通信を容易にSkype for Business、また、ハイブリッド接続の構成も必要Azure AD Connect。


## <a name="configuring-azure-ad-when-you-have-skype-for-business-server"></a>Skype for Business Server を使用している場合の Azure AD の構成 

### <a name="general-requirements"></a>一般的な要件 

Skype for Business Server のオンプレミス展開を Teams と共に存在するには、オンプレミス展開の特定の Active Directory 属性を Azure AD Connect を使用して Azure AD に同期する必要があります。 オンプレミス環境Azure AD Connectの存在を検出すると、既定で同期する必要な属性Skype for Business Server自動的に構成されます。 これらの属性には、ユーザー プリンシパル名などの一般的な ID 属性と、Skype For Business Server に固有の "msRTCSIP" が付く属性が含まれます。 属性の完全なセットは、同期時にAzure AD Connect一覧に表示されます[。属性](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized#teams-and-skype-for-business-online)は同期Azure Active Directory。

同期設定をカスタマイズする場合は、Azure AD Connectオブジェクトに対して次の属性が同期されている必要があります。
</br>

|属性|説明|
|---|---|
|msRTCSIP-PrimaryUserAddress| オンプレミス環境でのユーザーの sip アドレス|
|msRTCSIP-DeploymentLocator| ユーザーがオンプレミスまたはクラウドに保存されているかどうかを示します。|
|msRTCSIP-UserEnabled| ユーザーが SIP 機能を有効にするかどうか|
|||

</br>
</br>
さらに、オンプレミス展開を通じて電話システム属性を管理する場合は、次の属性も同期する必要があります。

|属性|説明|
|:---|:---|
|msRTCSIP-Line| ユーザーの電話番号|
|msRTCSIP-OptionFlags| ユーザーが音声機能を有効にしたかどうかを示します。|
|msRTCSIP-OwnerUrn| ハイブリッド アプリケーション エンドポイントの識別に使用|
|||

</br>
Microsoft では、ユーザー ID を含むすべてのフォレストと、ユーザー ID を含むフォレストを同期Skype for Business Server。 複数のフォレストにユーザーの ID が存在する場合は、Azure AD Connect で結合を行います。 このガイダンスに従うと、Azure AD Connect のコネクタまたは同期規則を変更していなければ、Azure AD Connect により、自動的に正しい属性が同期されます。 
  
ユーザー ID と Skype for Business Server 展開を含むすべてのフォレストから同期しない場合は、Teams または Skype for Business を使用するすべてのユーザー (オンプレミスまたはオンライン) に関連する ID と Skype for Business 属性が Azure AD に正しく設定されていることを確認する必要があります。 これにより、オンプレミスディレクトリの同期が追加で必要になります。 詳細については、「同期に同期[Azure AD Connect属性」を参照](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)Azure Active Directory。

属性をデータに入力するための適切な構成を確保する責任は、お客様Azure AD。 以下の点にご注意ください。 

- 標準以外の構成を使用してユーザーと同期Azure AD危険です。 標準以外の構成では、オンライン ディレクトリでデータが破損する可能性があります。

- 製品の進化に伴い、Microsoft は、関連するすべてのフォレストが同期される標準的な同期の構成を継続的に確認していきます。 カスタムの同期構成を使用しているお客様は、構成により Azure AD に正しい属性と値が提供されるように、責任をもってご確認ください。 

オンプレミスの Active Directory フォレストが 1 つでも複数のフォレストでも、Azure AD Connect は「トポロジ for Azure AD Connect」で説明されているさまざまなサポートされている[トポロジで使用できます](/azure/active-directory/hybrid/plan-connect-topologies)。 この方法の観点Skype for Business Server、次の 3 つのバリエーションがあります。 

1. 単一のフォレストで、権限のあるユーザー ID を含み、Skype for Business Server をホストしている。 

2. 複数のフォレストで、そのうち 1 つのフォレストのみが Skype for Business Server をホストしていて、他の 1 つ以上のフォレストが権限のあるユーザー ID を含んでいる (アカウント フォレスト)。 

3. 複数のフォレストで Skype for Business Server を複数配置している。 特定の要件が満たされている場合、組織は、これらの複数の展開を 1 つの組織に統合Microsoft 365できます。

### <a name="single-forest"></a>単一のフォレスト 

ユーザー アカウントと Skype for Business がすべて 1 つのフォレストにホストされている場合は、Azure AD Connect が、当該のフォレストから Azure AD にユーザーが同期されるように構成する必要があります。  既定では、適切な属性が自動的に同期され、Azure Active Directory。 構成を管理する組み込みの同期ルールやコネクタ (インストール ウィザードでは使用できない) を変更する必要があります。  

### <a name="multiple-forests-with-one-skype-for-business-deployment"></a>複数のフォレストで、1 つの Skype for Business Server を配置 

このシナリオは、通常、リソース フォレスト トポロジと呼ばれます。 ユーザーの権限のある ID が、1 つ以上のアカウント フォレストにホストされています。また、Skype for Business は別のリソース フォレストに配置されています (リソース フォレストには権限のあるユーザー ID もホストされます)。 以下の場合、Skype for Business ユーザーの権限のある ID は、通常、Skype for Business Server と同じフォレストか、または別のフォレストにあります。 

- アカウント フォレストの権限のある ID を持つユーザーは、リソース フォレスト (Skype for Business Serverが展開されている) で無効なユーザー オブジェクトとして表されます。 リソース フォレストの msRTCSIP-OriginatorSID 属性は、アカウント フォレストの SID と一致している必要があります。 詳細については[、「Configure a multi-forest environment for hybrid Skype for Business」 を参照してください](configure-a-multi-forest-environment-for-hybrid.md)。

- Skype for Business Server をホストするリソース フォレストは、アカウント フォレストを信頼している。  

- ID (アカウント フォレストから) と Skype for Business (リソース フォレストから) の両方に関連するすべてのユーザー オブジェクトと属性は、Azure AD Connect を通じて正しい値で Azure AD に同期されます。  

  複数フォレストのオンプレミスシナリオで適切なオブジェクトと属性を Azure AD[](configure-a-multi-forest-environment-for-hybrid.md)に同期するには、ユーザー アカウントを有効にしているすべてのフォレストと、Skype for Business を含むフォレストを同期するために Azure AD Connect を使用して強く推奨します。 すべてのフォレストから同期する場合、当該の ID を統合し、Azure AD に同期するように Azure AD Connect を構成する必要があります。 Azure AD Connect はこのシナリオを処理するように設計されており、その設定のために、ID を結合するアンカーの設定などの組み込みオプションがインストール ウィザードに用意されています。 複数のディレクトリにユーザー **ID** が存在し、--> ObjectSID 属性と **msExchangeMasterAccountSID** 属性を使用して一致します。


### <a name="multiple-skype-for-business-server-deployments-in-multiple-forests"></a>複数のフォレストでの Skype for Business Server の複数配置 

このシナリオでは、複数のフォレストがあります。各フォレストにはSkype for Business Server 1 つのフォレストMicrosoft 365があります。 グループを含むSkype for Business Serverは、その組織のAzure ADに同期Azure AD Connect。 指定した時間に Skype for Business ハイブリッド用に構成できるフォレストは最大でも 1 つだけです。 フォレストでハイブリッドを有効にする前に [、disable-csonlineSipDomain](/powershell/module/skype/disable-csonlinesipdomain)を使用して、他のすべてのフォレストのすべての SIP ドメインを無効にする必要があります。 詳細については、「クラウド統合[for Teams」をSkype for Business。](cloud-consolidation.md)


## <a name="related-information"></a>関連情報

- [ハイブリッド ID とは](/azure/active-directory/hybrid/whatis-hybrid-identity)

- [Azure AD Connect 同期: 同期を理解してカスタマイズする](/azure/active-directory/hybrid/how-to-connect-sync-whatis)

- [Azure AD Connect のトポロジ](/azure/active-directory/hybrid/plan-connect-topologies)

- [Azure AD Connect同期: 同期された属性Azure Active Directory](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)
