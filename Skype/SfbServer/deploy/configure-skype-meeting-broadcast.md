---
title: Skype 会議ブロードキャストを使用できるようにオンプレミス展開を構成する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: '概要: オンプレミスの Skype for Business Server ハイブリッド展開用に Skype 会議ブロードキャストを構成するために実行する必要のある手順について説明します。'
ms.openlocfilehash: 8bdbb163f5ef867711ce109bc923ba0ec8401ffa
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41790945"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a>Configure your on-premises deployment for Skype Meeting Broadcast
 
**概要:** オンプレミスの Skype for Business Server ハイブリッド展開用に Skype 会議ブロードキャストを構成するために必要な手順について説明します。
  
Skype 会議ブロードキャストは、Office 365 の一部であるオンラインサービスです。 Skype for Business Server をオンプレミスで実行していて、環境で Skype 会議ブロードキャストを使用する場合は、このトピックの構成手順を実行する必要があります。 始める前に、お客様の環境が Skype for Business Online とのハイブリッド用に構成されている必要があります。 詳細については、「[Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)」、および「[Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)」を参照してください。
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a>Skype 会議ブロードキャストのハイブリッド環境を構成する

Skype 会議ブロードキャストの環境を準備するには、次の手順を実行する必要があります。
  
- Skype for Business Online のリソースとのフェデレーションを構成する
    
- SIP フェデレーション ドメインを構成する
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a>Skype for Business Online のリソースとのフェデレーションを構成する

Skype for Business Online のリソースとのフェデレーションを有効にするには、SIP フェデレーションプロバイダーの外部アクセスを構成する必要があります。 Skype for Business Server コントロールパネルを使用してこれを行うには、次の手順を実行します。
  
1. Skype for Business Server コントロールパネルを起動し、左側の [**外部アクセス**] を選択します。
    
2. [**SIP フェデレーション プロバイダー**] を選択し、[**新規**] をクリックします。
    
3. 次の設定を使用して新しいプロバイダーを構成します。
    
|||
|:-----|:-----|
|**このプロバイダーとの通信を有効にする:** <br/> |オン  <br/> |
|**[プロバイダー名]:** <br/> |LyncOnlineResources  <br/> |
|**[アクセス エッジ サービス (FQDN)]:** <br/> |sipfed.resources.lync.com  <br/> |
|**[既定の確認レベル]:** <br/> |このプロバイダーを使うすべてのユーザーとの通信を許可する  <br/> |
   
Skype for Business Server 管理シェルで次のコマンドレットを実行して、Skype for business Online のリソースとのフェデレーションを有効にすることもできます。
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a>SIP フェデレーション ドメインを構成する

次に、SIP フェデレーションドメインを許可ドメインリストに追加する必要があります。 一覧にある 4 つのドメインのそれぞれに対して以下の手順を繰り返します。 これらのドメインは、Skype for Business Online で使用される地域データセンターのために用意されています。
  
1. Skype for Business Server コントロールパネルを起動し、左側の [**外部アクセス**] を選択します。
    
2. [**SIP フェデレーション ドメイン**] を選択し、[**新規**] をクリックします。
    
3. [**ドメイン名 (または FQDN):**] にはドメインを入力し、以下の各ドメインにこの手順を繰り返します。
    
   - noammeetings.lync.com
    
   - emeameetings.lync.com
    
   - apacmeetings.lync.com
    
   - resources.lync.com
    
また、Skype for Business Server 管理シェルで次のコマンドレットを実行して、SIP フェデレーションドメインの外部アクセスを構成することもできます。
  
```powershell
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

これらの構成手順が完了したら、展開で Skype 会議ブロードキャストを使い始めることができます。 Skype 会議ブロードキャストの詳細については、「 [Skype 会議ブロードキャストとは](https://go.microsoft.com/fwlink/?LinkId=617071)」および「 [Skype 会議ブロードキャスト管理者ガイド](https://go.microsoft.com/fwlink/?LinkId=617075)」を参照してください。
  

