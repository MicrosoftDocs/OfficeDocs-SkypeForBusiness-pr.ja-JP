---
title: Skype 会議ブロードキャストを使用できるようにオンプレミス展開を構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: '概要: は、ハイブリッド展開のビジネスのサーバーの設置型の Skype の Skype 会議のブロードキャストを構成するのには実行する必要がある手順について説明します。'
ms.openlocfilehash: 4eb117715905a9d371b725c8da7a992b9fdee6b4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894205"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a>Configure your on-premises deployment for Skype Meeting Broadcast
 
**の概要:** 設置型の Skype ビジネス サーバー ハイブリッド展開用の Skype 会議のブロードキャストを構成するために実行する必要がある手順について説明します。
  
Skype 会議のブロードキャストは、Office 365 の一部であるオンライン サービスです。 ビジネス サーバー設置型の Skype を実行している環境で Skype 会議のブロードキャストを使用する場合は、このトピックで構成手順を実行する必要があります。 作業を開始する前に、環境をビジネス オンラインの Skype でのハイブリッドを構成する必要があります。 詳細については、「[Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)」、および「[Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)」を参照してください。
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a>Skype 会議のブロードキャストに、ハイブリッド環境を構成します。

Skype 会議をブロードキャストするため、環境を準備するのには次の操作をする必要があります。
  
- Skype でのビジネスのオンライン リソースのフェデレーションを構成します。
    
- SIP フェデレーション ドメインを構成する
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a>Skype でのビジネスのオンライン リソースのフェデレーションを構成します。

Skype でのビジネスのオンライン リソースのフェデレーションを有効にするには、SIP フェデレーション プロバイダーの外部アクセスを構成する必要があります。 このビジネス サーバーのコントロール パネルの Skype を使用して以下の手順。
  
1. ビジネス サーバーのコントロール パネルの Skype を起動し、左上の**外部からのアクセス**を選択します。
    
2. [**SIP フェデレーション プロバイダー**] を選択し、[**新規**] をクリックします。
    
3. 次の設定を使用して新しいプロバイダーを構成します。
    
|||
|:-----|:-----|
|**このプロバイダーとの通信を有効にします。** <br/> |オン  <br/> |
|**[プロバイダー名]:** <br/> |LyncOnlineResources  <br/> |
|**[アクセス エッジ サービス (FQDN)]:** <br/> |sipfed.resources.lync.com  <br/> |
|**[既定の確認レベル]:** <br/> |このプロバイダーを使うすべてのユーザーとの通信を許可する  <br/> |
   
また、Skype でビジネス サーバー管理シェルの次のコマンドレットを実行して、Skype でのビジネスのオンライン リソースのフェデレーションを有効にできます。
  
```
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a>SIP フェデレーション ドメインを構成する

次に、フェデレーションする SIP ドメインを許可されているドメイン一覧に追加する必要があります。 一覧にある 4 つのドメインのそれぞれに対して以下の手順を繰り返します。 これらのドメインは、地域のデータのオンライン ビジネスで使用されている Skype を中央揃えにします。
  
1. ビジネス サーバーのコントロール パネルの Skype を起動し、左上の**外部からのアクセス**を選択します。
    
2. [**SIP フェデレーション ドメイン**] を選択し、[**新規**] をクリックします。
    
3. [**ドメイン名 (または FQDN):**] にはドメインを入力し、以下の各ドメインにこの手順を繰り返します。
    
   - noammeetings.lync.com
    
   - emeameetings.lync.com
    
   - apacmeetings.lync.com
    
   - resources.lync.com
    
Skype でビジネス サーバー管理シェルの次のコマンドレットを実行して、フェデレーションする SIP ドメインの外部アクセスを構成することも。
  
```
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

構成手順を完了したら、環境で Skype 会議のブロードキャストを使用を開始できます。 Skype 会議のブロードキャストの詳細についてを参照してください[Skype の会議のブロードキャストとは何ですか?](https://go.microsoft.com/fwlink/?LinkId=617071)と[Skype 会議のブロードキャスト管理者ガイド](https://go.microsoft.com/fwlink/?LinkId=617075)です。
  

