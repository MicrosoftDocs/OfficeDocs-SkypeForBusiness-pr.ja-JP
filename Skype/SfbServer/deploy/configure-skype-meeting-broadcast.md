---
title: 会議ブロードキャスト用にオンプレミス展開Skype構成する
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - Ent_O365_Hybrid
  - Ent_O365_Hybrid_Top
  - IT_Skype16
  - IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: '概要: ハイブリッド展開用に会議ブロードキャストを構成するためにSkypeする必要がある手順Skype for Business Server説明します。'
---

# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a>会議ブロードキャスト用にオンプレミス展開Skype構成する
 
**概要:** ハイブリッド展開用に会議ブロードキャストを構成するためにSkypeする必要がある手順Skype for Business Server説明します。
  
Skype会議ブロードキャストは、会議の一部であるオンライン Office 365。 オンプレミスで Skype for Business Serverを実行し、環境で Skype 会議ブロードキャストを使用する場合は、このトピックの構成手順に従う必要があります。 開始する前に、環境をオンラインのハイブリッド用に構成Skype for Business必要があります。 詳細については、「Plan [hybrid connectivity](../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) between Skype for Business Server and Skype for Business Online」および「Deploy hybrid connectivity between Skype for Business Server and [Skype for Business Online」を参照してください](../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)。
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a>会議ブロードキャストのハイブリッド環境Skype構成する

会議ブロードキャストの環境を準備するには、次のSkype必要があります。
  
- オンライン リソースとのフェデレーションSkype for Business構成する
    
- SIP フェデレーション ドメインの構成
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a>オンライン リソースとのフェデレーションSkype for Business構成する

オンライン リソースとのフェデレーションSkype for Businessするには、SIP フェデレーション プロバイダーの外部アクセスを構成する必要があります。 この操作を行うには、次の手順に従Skype for Business Serverコントロール パネルを使用します。
  
1. [コントロール パネルSkype for Business Serverを起動し、左側 **の [外部アクセス]** を選択します。
    
2. [ **SIP フェデレーション プロバイダー] を選択し、[** 新規] を **クリックします**。
    
3. 次の設定で新しいプロバイダーを構成します。
    
   - **このプロバイダーとの通信を有効にする:** [選択]
   - **プロバイダー名:** LyncOnlineResources
   - **Access Edge Service (FQDN): sipfed.resources.lync.com**
   - **既定の検証レベル:** ユーザーがこのプロバイダーを使用してすべてのユーザーと通信できます。 
   
また、管理シェルで次Skype for Businessコマンドレットを実行して、オンライン リソースとのフェデレーションSkype for Business Serverできます。
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a>SIP フェデレーション ドメインの構成

次に、SIP フェデレーション ドメインを許可されたドメイン リストに追加する必要があります。 リストされている各ドメインに対してこれらの手順を繰り返し、4 つの新しい SIP フェデレーション ドメインを作成します。 これらのドメインには、オンラインで使用される地域データ センター Skype for Businessがあります。
  
1. [コントロール パネルSkype for Business Serverを起動し、左側 **の [外部アクセス]** を選択します。
    
2. [ **SIP フェデレーション ドメイン] を選択し、[** 新規] を **クリックします**。
    
3. [ドメイン **名 ] (または FQDN):** にドメインを入力し、次の各ドメインに対してこの手順を繰り返します。
    
   - noammeetings.lync.com
    
   - emeameetings.lync.com
    
   - apacmeetings.lync.com
    
   - resources.lync.com
    
SIP フェデレーション ドメインの外部アクセスを構成するには、SIP 管理シェルで次のコマンドレットSkype for Business Server実行します。
  
```powershell
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

これらの構成手順を完了したら、展開で会議ブロードキャストSkypeを開始できます。 会議ブロードキャストの詳細Skype、「会議ブロードキャストとは」および「[](https://go.microsoft.com/fwlink/?LinkId=617071)Skype Skypeブロードキャスト管理ガイド」を[参照してください](../../SfbOnline/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md)。
