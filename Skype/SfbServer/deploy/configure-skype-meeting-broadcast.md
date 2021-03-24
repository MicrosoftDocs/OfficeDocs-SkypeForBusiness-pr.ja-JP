---
title: Skype 会議ブロードキャストのオンプレミス展開を構成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: '概要: オンプレミスの Skype for Business Server ハイブリッド展開用に Skype 会議ブロードキャストを構成するために実行する必要がある手順について説明します。'
ms.openlocfilehash: b70272ee90146bdac87264acf0c7673b8def05c2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103693"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a>Skype 会議ブロードキャストのオンプレミス展開を構成する
 
**概要:** オンプレミスの Skype for Business Server ハイブリッド展開用に Skype 会議ブロードキャストを構成するために実行する必要がある手順について説明します。
  
Skype 会議ブロードキャストは、365 の一部であるOfficeです。 Skype for Business Server をオンプレミスで実行し、環境で Skype 会議ブロードキャストを使用する場合は、このトピックの構成手順に従う必要があります。 開始する前に、Skype for Business Online とのハイブリッド環境を構成する必要があります。 詳細については [、「Skype for Business Server](../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) と Skype for Business Online 間のハイブリッド接続を計画する」および [「Skype for Business Server](../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)と Skype for Business Online のハイブリッド接続を展開する」を参照してください。
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a>Skype 会議ブロードキャストのハイブリッド環境を構成する

Skype 会議ブロードキャストの環境を準備するには、次の手順を実行する必要があります。
  
- Skype for Business Online リソースとのフェデレーションを構成する
    
- SIP フェデレーション ドメインの構成
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a>Skype for Business Online リソースとのフェデレーションを構成する

Skype for Business Online リソースとのフェデレーションを有効にするには、SIP フェデレーション プロバイダーの外部アクセスを構成する必要があります。 Skype for Business Server コントロール パネルを使用してこれを行うには、次の手順を実行します。
  
1. Skype for Business Server コントロール パネルを起動し、左側の **[外部アクセス]** を選択します。
    
2. [SIP **フェデレーション プロバイダー] を選択し、[** 新規] を **クリックします**。
    
3. 次の設定で新しいプロバイダーを構成します。
    
|||
|:-----|:-----|
|**このプロバイダーとの通信を有効にする:** <br/> |選択済み  <br/> |
|**プロバイダー名:** <br/> |LyncOnlineResources  <br/> |
|**Access Edge Service (FQDN):** <br/> |sipfed.resources.lync.com  <br/> |
|**既定の検証レベル:** <br/> |ユーザーがこのプロバイダーを使用してすべてのユーザーと通信できます。  <br/> |
   
Skype for Business Server 管理シェルで次のコマンドレットを実行して、Skype for Business Online リソースとのフェデレーションを有効にすることもできます。
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a>SIP フェデレーション ドメインの構成

次に、SIP フェデレーション ドメインを許可されたドメイン リストに追加する必要があります。 リストされている各ドメインに対してこれらの手順を繰り返し、4 つの新しい SIP フェデレーション ドメインを作成します。 これらのドメインには、Skype for Business Online で使用される地域データ センターが含まれます。
  
1. Skype for Business Server コントロール パネルを起動し、左側の **[外部アクセス]** を選択します。
    
2. [SIP **フェデレーション ドメイン] を選択し、[** 新規] を **クリックします**。
    
3. ドメイン名 **(または FQDN) の場合は**、ドメインを入力し、次の各ドメインに対してこの手順を繰り返します。
    
   - noammeetings.lync.com
    
   - emeameetings.lync.com
    
   - apacmeetings.lync.com
    
   - resources.lync.com
    
Skype for Business Server 管理シェルで次のコマンドレットを実行して、SIP フェデレーション ドメインの外部アクセスを構成することもできます。
  
```powershell
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

これらの構成手順を完了したら、展開で Skype 会議ブロードキャストの使用を開始できます。 Skype 会議ブロードキャストの詳細については、「Skype[](https://go.microsoft.com/fwlink/?LinkId=617071)会議ブロードキャストとは」および[「Skype 会議ブロードキャスト管理ガイド」を参照してください](../../SfbOnline/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md)。
