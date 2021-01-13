---
title: Skype for Business Server の DNS レコードを作成する
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 798a663c-0b63-4f75-b0a3-9c553cef8c5f
description: '概要: Skype for Business Server のインストール用に DNS を構成し、DNS レコードを作成する方法について学習します。 Microsoft Evaluation Center から Skype for Business Server の無料試用版を次の場所からダウンロードします  https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 。'
ms.openlocfilehash: 3808216e0732d6e3af2f32e27d79d78727ddc105
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812137"
---
# <a name="create-dns-records-for-skype-for-business-server"></a>Skype for Business Server の DNS レコードを作成する
 
**概要:** Skype for Business Server のインストール用に DNS を構成し、DNS レコードを作成する方法について学習します。 Microsoft Evaluation Center から Skype for Business Server の無料試用版を次の場所からダウンロードします [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) 。
  
Skype for Business Server が正常に動作するには、多数のドメイン ネーム システム (DNS) 設定を設定する必要があります。 これは、クライアントがサービスにアクセスする方法を知り、サーバーが互いを知る必要があるという設定です。 これらの設定は、展開ごとに 1 回だけ完了する必要があります。DNS エントリを割り当てると、ドメイン全体で使用できます。 手順 1. ~ 5. は任意の順序で実行できます。 ただし、手順 6、7、および 8 は、図に示されている順序、および手順 1 ~ 5 の後に実行する必要があります。 DNS レコードの作成は、手順 5/8 で構成されます。 DNS の計画の詳細については [、「Environmental requirements for Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) or Server [requirements for Skype for Business Server 2019](../../../SfBServer2019/plan/system-requirements.md)」を参照してください。
  
> [!IMPORTANT]
> これは、Windows Server DNS 環境で DNS レコードを作成する方法の一例にすすむ点に注意してください。 Skype for Business Server には他にも多くの DNS エントリが必要であり、DNS レコードを作成する手順は、組織で DNS を管理するために使用しているシステムによって異なります。 DNS の要件の完全な一覧については、Skype for Business Server の [DNS 要件を参照してください](../../plan-your-deployment/network-requirements/dns.md)。 
  
![概要図](../../media/d2fc733c-6a80-4d17-a02f-93b8c4bfb999.png)
  
## <a name="configure-dns"></a>DNS の構成

Skype for Business Server が正常に動作し、ユーザーがアクセスするには、DNS レコードが必要です。
  
この例では、pool.contoso.local という名前の DNS 負荷分散 FQDN を使用しています。 このプールは、Skype for Business Server Enterprise Edition を実行している 3 台のサーバーで構成されます。 Standard Edition フロントエンド サーバーには、1 台のサーバーしか含めできません。 Standard Edition を使用する場合、次の例に示すように、DNS 負荷分散されたサーバー プールを作成する代わりに、フロントエンドの役割を参照する場合にのみ、単一の Standard Edition サーバーの完全修飾ドメイン名 (FQDN) を使用します。 フロントエンドの役割のみを使用するこの簡単な例には、次の表に示す DNS エントリが含まれています。 特定の DNS 要件を計画するには [、Skype for Business Server の DNS 要件を参照してください](../../plan-your-deployment/network-requirements/dns.md)。 
  
 
|**説明**|**Record type**|**名前**|**解決先**|**負荷分散の種類**|
|:-----|:-----|:-----|:-----|:-----|
|内部 Web サービスの FQDN  <br/> |A  <br/> |webint.contoso.local  <br/> |内部 Web サービスの VIP  <br/> |サポートされているソフトウェアとハードウェア  <br/> |
|プールの FQDN  <br/> |A  <br/> |pool.contoso.local  <br/> |サーバー SFB01 の IP アドレス  <br/> |DNS  <br/> |
|SFB01 FQDN  <br/> |A  <br/> |SFB01.contoso.local  <br/> |サーバー SFB01 の IP アドレス  <br/> |DNS  <br/> |
|プールの FQDN  <br/> |A  <br/> |pool.contoso.local  <br/> |サーバー SFB02 の IP アドレス  <br/> |DNS  <br/> |
|SFB02 FQDN  <br/> |A  <br/> |SFB02.contoso.local  <br/> |サーバー SFB02 の IP アドレス  <br/> |DNS  <br/> |
|プールの FQDN  <br/> |A  <br/> |pool.contoso.local  <br/> |サーバー SFB03 の IP アドレス  <br/> |DNS  <br/> |
|SFB03 FQDN  <br/> |A  <br/> |SFB03.contoso.local  <br/> |サーバー SFB03 の IP アドレス  <br/> |DNS  <br/> |
|Skype for Business の自動検出  <br/> |A  <br/> |lyncdiscoverinternal.contoso.local  <br/> |内部 Web サービスの VIP  <br/> |サポートされているソフトウェアとハードウェア  <br/> |
|会議の簡易 URL  <br/> |A  <br/> |meet.contoso.local  <br/> |内部 Web サービスの VIP  <br/> |サポートされているソフトウェアとハードウェア  <br/> |
|ダイヤルイン簡易 URL  <br/> |A  <br/> |dialin.contoso.local  <br/> |内部 Web サービスの VIP  <br/> |サポートされているソフトウェアとハードウェア  <br/> |
|Web スケジューラの簡易 URL  <br/> |A  <br/> |scheduler.contoso.local  <br/> |内部 Web サービスの VIP  <br/> |サポートされているソフトウェアとハードウェア  <br/> |
|管理簡易 URL  <br/> |A  <br/> |admin.contoso.local  <br/> |内部 Web サービスの VIP  <br/> |サポートされているソフトウェアとハードウェア  <br/> |
|従来の検出  <br/> |SRV  <br/> |_sipinternaltls._tcp.contoso.local  <br/> |プールの FQDN (ポート 5061)  <br/> |N/A  <br/> |
   
### <a name="create-dns-records"></a>DNS レコードの作成

1. DNS サーバーにログオンし、サーバー マネージャーを **開きます**。
    
2. [ツール **] ドロップダウン メニュー** をクリックし **、[DNS] をクリックします**。
    
3. SIP ドメインのコンソール ツリーで、[前方参照ゾーン] を展開し、Skype for Business Server をインストールする SIP ドメインを展開します。
    
4. 図に示すように、SIP ドメインを右クリックし、新しいホスト (A または **AAAA)** を選択します。
    
     ![新しい A レコードの選択](../../media/f89c5c1f-b5b7-428c-a6e3-2bcd12e878c3.png)
  
5. [名前 **]** ボックスにホスト レコードの名前を入力します (ドメイン名が自動的に追加されます)。
    
6. **[IP** アドレス] ボックスに、個々のフロントエンド サーバーの IP アドレスを入力し、[関連付けられたポインター **(PTR)** レコードを作成する] または [すべての認証されたユーザーが同じ所有者名の **DNS** レコードを更新する許可を与える] (該当する場合) を選択します。 これは、WEB サービスを除くすべてのトラフィックの負荷分散に DNS が使用されている場合を前提とします。 この例では、表に示すように 3 台のフロントエンド サーバーがあります。
    
   |**サーバー名**|**Type**|**Data**|
   |:-----|:-----|:-----|
   |SFB01  <br/> |ホスト (A)  <br/> |10.0.0.5  <br/> |
   |SFB02  <br/> |ホスト (A)  <br/> |10.0.0.6  <br/> |
   |SFB03  <br/> |ホスト (A)  <br/> |10.0.0.7  <br/> |
   
7. 次に、プールの DNS 負荷分散エントリを作成します。 DNS 負荷分散を使用すると、DNS は同じ DNS プール名を使用しながら、プール内の個々のサーバーに要求を送信できます。 DNS と負荷分散の詳細については、Skype for Business Server の [DNS 要件を参照してください](../../plan-your-deployment/network-requirements/dns.md)。 
    
    > [!NOTE]
    > 複数のサーバーを一緒にプールする方法は、Enterprise Edition 展開でのみ使用できます。 単一の Enterprise Server または Standard Edition サーバーを展開する場合は、単一サーバーの A レコードのみを作成する必要があります。 
  
    たとえば、pool.contoso.local という名前のプールと 3 つのフロントエンド サーバーがある場合は、次の DNS エントリを作成します。
    
   |**FQDN**|**Type**|**Data**|
   |:-----|:-----|:-----|
   |pool.contoso.local  <br/> |ホスト (A)  <br/> |10.0.0.5  <br/> |
   |pool.contoso.local  <br/> |ホスト (A)  <br/> |10.0.0.6  <br/> |
   |pool.contoso.local  <br/> |ホスト (A)  <br/> |10.0.0.7  <br/> |
   
8. 計画した展開のすべてのサーバーの A レコードの作成を続行します。 
    
9. 従来の検出用のサービス レコード (SRV) レコードを作成するには、SIP ドメインを右クリックし、[その他の新しいレコード] **を選択します**。
    
10. [**リソース レコードの種類を選択**] の [**サービス ロケーション (SRV)**] をクリックし、[**レコードの作成**] をクリックします。
    
11. "**サービス**" フィールドをクリックし、「**_sipinternaltls**」と入力します。
    
12. "**プロトコル**" フィールドをクリックし、「**_tcp**」と入力します。
    
13. "**ポート番号**" フィールドをクリックし、「**5061**」と入力します。
    
14. [ **このサービスを提供するホスト] を** クリックし、プールまたは Standard Edition サーバーの FQDN を入力します。
    
     ![新しいリソース レコード ダイアログのスクリーンショット。](../../media/54b1aac5-a2ec-41fe-90c0-02eaeaa9d1b4.png)
  
15. [**OK**] をクリックしてから、[**完了**] をクリックします。
    
### <a name="verify-dns-records"></a>DNS レコードを確認する

1. Authenticated Users グループのメンバーであるアカウントまたは同等のアクセス許可を持つアカウントを使用して、ドメインのクライアント コンピューターにログオンします。
    
2. [ **スタート] ボタン** をクリックし **、「cmd」** と入力して Enter キーを押します。
    
3. **「nslookup」または \<FQDN of the Front End pool\> 「Enter」** **\<FQDN of the Standard Edition server or single Enterprise Edition server\>** と入力して、Enter キーを押します。
    
4. 展開の残りの A レコードを引き続き確認します。
    
5. レガシ クライアントをサポートし、SRV レコードを作成している場合は **、nslookup** プロンプトで **「set type=srv」** と入力して確認し、Enter キーを押します。
    
6. **「_sipinternaltls._tcp」と入力します。*domain***(例: _sipinternaltls._tcp.contoso.local)、Enter キーを押します。
    
7. 予想される出力は、図に示す出力と同様である必要があります。 すべての DNS レコードがサンプル出力に表示されるのではなく、すべてのレコードを検証する必要があります。 
    
     ![dns 設定を確認します。](../../media/4fcaa70f-7717-4939-9652-d2048d6293cc.png)
  

