---
title: Skype for Business Serverの DNS レコードを作成する
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 798a663c-0b63-4f75-b0a3-9c553cef8c5f
description: '概要: DNS を構成し、Skype for Business Serverのインストール用に DNS レコードを作成する方法について説明します。'
ms.openlocfilehash: 5e974df94aba8b879c672250b69432dfd0a5f1f3
ms.sourcegitcommit: e99471689ff60f9ab1095bc075f8b4c5569c9634
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/02/2022
ms.locfileid: "65860538"
---
# <a name="create-dns-records-for-skype-for-business-server"></a>Skype for Business Serverの DNS レコードを作成する
 
**概要：** SKYPE FOR BUSINESS SERVERのインストール用に DNS を構成し、DNS レコードを作成する方法について説明します。
  
Skype for Business Serverが正常に機能するには、多くのドメイン ネーム システム (DNS) 設定が設定されている必要があります。 これは、クライアントがサービスにアクセスする方法を知り、サーバーが互いについて知ることができるようにするためです。 DNS エントリを割り当てるとドメイン全体で使用できるため、これらの設定はデプロイごとに 1 回だけ完了する必要があります。 手順 1 ~ 5 は、任意の順序で実行できます。 ただし、図に示すように、手順 6、7、および 8 を順番に実行し、手順 1 ~ 5 の後に実行する必要があります。 DNS レコードの作成は、手順 5/ 8 で構成されます。 DNS の計画の詳細については、「[Skype for Business Serverの環境要件](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)または [Skype for Business Server 2019 のサーバー要件](../../../SfBServer2019/plan/system-requirements.md)」を参照してください。
  
> [!IMPORTANT]
> これは、Windows サーバーの DNS 環境で DNS レコードを作成する方法の例に過ぎないことに注意してください。 Skype for Business Serverには他にも多くの DNS エントリが必要であり、DNS レコードを作成する手順は、組織内の DNS の管理に使用しているシステムによって異なります。 DNS の要件の完全な一覧については、「[Skype for Business Serverの DNS 要件」を](../../plan-your-deployment/network-requirements/dns.md)参照してください。 
  
![概要図。](../../media/d2fc733c-6a80-4d17-a02f-93b8c4bfb999.png)
  
## <a name="configure-dns"></a>DNS の構成

Skype for Business Serverが正常に動作し、ユーザーがアクセスできるようにするには、DNS レコードが必要です。
  
この例では、pool.contoso.local という名前の DNS 負荷分散 FQDN を使用しています。 このプールは、Skype for Business Server Enterprise Editionを実行している 3 台のサーバーで構成されます。 Standard Edition フロントエンド サーバーには、1 台のサーバーのみを含めることができます。 Standard Editionを使用すると、次の例に示すように、サーバーの DNS 負荷分散プールを作成するのではなく、フロントエンド ロールを参照するときに、単一のStandard Edition サーバーの完全修飾ドメイン名 (FQDN) のみを使用します。 フロントエンド ロールのみを使用するこの簡単な例には、次の表に示す DNS エントリが含まれています。 特定の DNS 要件を計画するには、[Skype for Business Serverの DNS 要件に関するページを](../../plan-your-deployment/network-requirements/dns.md)参照してください。 
  
 
|**説明**|**Record type**|**名前**|**解決先**|**負荷分散の種類**|
|:-----|:-----|:-----|:-----|:-----|
|内部 Web サービス FQDN  <br/> |A  <br/> |webint.contoso.local  <br/> |内部 Web サービスの VIP  <br/> |サポートされているソフトウェアとハードウェア  <br/> |
|プールの FQDN  <br/> |A  <br/> |pool.contoso.local  <br/> |サーバー SFB01 の IP アドレス  <br/> |DNS  <br/> |
|SFB01 FQDN  <br/> |A  <br/> |SFB01.contoso.local  <br/> |サーバー SFB01 の IP アドレス  <br/> |DNS  <br/> |
|プールの FQDN  <br/> |A  <br/> |pool.contoso.local  <br/> |サーバー SFB02 の IP アドレス  <br/> |DNS  <br/> |
|SFB02 FQDN  <br/> |A  <br/> |SFB02.contoso.local  <br/> |サーバー SFB02 の IP アドレス  <br/> |DNS  <br/> |
|プールの FQDN  <br/> |A  <br/> |pool.contoso.local  <br/> |サーバー SFB03 の IP アドレス  <br/> |DNS  <br/> |
|SFB03 FQDN  <br/> |A  <br/> |SFB03.contoso.local  <br/> |サーバー SFB03 の IP アドレス  <br/> |DNS  <br/> |
|Skype for Business自動検出  <br/> |A  <br/> |lyncdiscoverinternal.contoso.local  <br/> |内部 Web サービスの VIP  <br/> |サポートされているソフトウェアとハードウェア  <br/> |
|会議のシンプルな URL  <br/> |A  <br/> |meet.contoso.local  <br/> |内部 Web サービスの VIP  <br/> |サポートされているソフトウェアとハードウェア  <br/> |
|ダイヤルイン簡易 URL  <br/> |A  <br/> |dialin.contoso.local  <br/> |内部 Web サービスの VIP  <br/> |サポートされているソフトウェアとハードウェア  <br/> |
|Web Scheduler の単純な URL  <br/> |A  <br/> |scheduler.contoso.local  <br/> |内部 Web サービスの VIP  <br/> |サポートされているソフトウェアとハードウェア  <br/> |
|管理の簡単な URL  <br/> |A  <br/> |admin.contoso.local  <br/> |内部 Web サービスの VIP  <br/> |サポートされているソフトウェアとハードウェア  <br/> |
|レガシ検出  <br/> |SRV  <br/> |_sipinternaltls._tcp.contoso.local  <br/> |プール FQDN (ポート 5061)  <br/> |該当なし  <br/> |
   
### <a name="create-dns-records"></a>DNS レコードの作成

1. DNS サーバーにログオンし、サーバー マネージャーを開 **きます**。
    
2. [ **ツール** ] ドロップダウン メニューをクリックし、[ **DNS**] をクリックします。
    
3. SIP ドメインのコンソール ツリーで、**前方参照ゾーン** を展開し、Skype for Business Serverがインストールされる SIP ドメインを展開します。
    
4. 図に示すように、SIP ドメインを右クリックし、 **新しいホスト (A または AAAA)** を選択します。
    
     ![新しい A レコードを選択します。](../../media/f89c5c1f-b5b7-428c-a6e3-2bcd12e878c3.png)
  
5. [ **名前]** ボックスに、ホスト レコードの名前を入力します (ドメイン名は自動的に追加されます)。
    
6. [ **IP アドレス] ボックス** に、個々のフロントエンド サーバーの IP アドレスを入力し、 **関連付けられたポインター (PTR) レコードの作成** または **認証されたユーザーが同じ所有者名で DNS レコードを更新することを許可** する (該当する場合) を選択します。 これは、WEB サービスを除くすべてのトラフィックの負荷分散に DNS が使用されることを前提としています。 この例では、表に示すように 3 つのフロントエンド サーバーがあります。
    
   |**サーバー名**|**Type**|**Data**|
   |:-----|:-----|:-----|
   |SFB01  <br/> |ホスト (A)  <br/> |10.0.0.5  <br/> |
   |SFB02  <br/> |ホスト (A)  <br/> |10.0.0.6  <br/> |
   |SFB03  <br/> |ホスト (A)  <br/> |10.0.0.7  <br/> |
   
7. 次に、プールの DNS 負荷分散エントリを作成します。 DNS 負荷分散を使用すると、DNS は同じ DNS プール名を使用しながら、プール内の個々のサーバーに要求を送信できます。 DNS と負荷分散の詳細については、[Skype for Business Serverの DNS 要件に関するページを](../../plan-your-deployment/network-requirements/dns.md)参照してください。 
    
    > [!NOTE]
    > 複数のサーバーをまとめてプールすることは、Enterprise Editionデプロイでのみ使用できます。 単一のEnterprise サーバーまたはStandard Edition サーバーをデプロイする場合は、単一のサーバーの A レコードのみを作成する必要があります。 
  
    たとえば、pool.contoso.local という名前のプールと 3 つのフロントエンド サーバーがある場合は、次の DNS エントリを作成します。
    
   |**FQDN**|**Type**|**Data**|
   |:-----|:-----|:-----|
   |pool.contoso.local  <br/> |ホスト (A)  <br/> |10.0.0.5  <br/> |
   |pool.contoso.local  <br/> |ホスト (A)  <br/> |10.0.0.6  <br/> |
   |pool.contoso.local  <br/> |ホスト (A)  <br/> |10.0.0.7  <br/> |
   
8. 計画されたデプロイ内のすべてのサーバーの A レコードの作成を続行します。 
    
9. レガシ検出のサービス レコード (SRV) レコードを作成するには、SIP ドメインを右クリックし、[ **その他の新しいレコード**] を選択します。
    
10. [**リソース レコードの種類を選択**] の [**サービス ロケーション (SRV)**] をクリックし、[**レコードの作成**] をクリックします。
    
11. "**サービス**" フィールドをクリックし、「**_sipinternaltls**」と入力します。
    
12. "**プロトコル**" フィールドをクリックし、「**_tcp**」と入力します。
    
13. "**ポート番号**" フィールドをクリックし、「**5061**」と入力します。
    
14. **[このサービスを提供するホスト**] をクリックし、プールまたはStandard Edition サーバーの FQDN を入力します。
    
     ![[新しいリソース レコード] ダイアログのスクリーンショット。](../../media/54b1aac5-a2ec-41fe-90c0-02eaeaa9d1b4.png)
  
15. [**OK**] をクリックしてから、[**完了**] をクリックします。
    
### <a name="verify-dns-records"></a>DNS レコードを確認する

1. Authenticated Users グループのメンバーであるアカウントまたは同等のアクセス許可を持つアカウントを使用して、ドメインのクライアント コンピューターにログオンします。
    
2. [ **スタート]** をクリックし、「 **cmd」** と入力して Enter キーを押します。
    
3. **nslookup \<FQDN of the Front End pool\>** または **\<FQDN of the Standard Edition server or single Enterprise Edition server\>** 入力し、Enter キーを押します。
    
4. 引き続き、デプロイの残りの A レコードを確認します。
    
5. レガシ クライアントをサポートしていて SRV レコードを作成している場合は、**nslookup** プロンプトで **set type=srv** と入力して確認し、Enter キーを押します。
    
6. **_sipinternaltls._tcp と入力します。*ドメイン***(たとえば、_sipinternaltls._tcp.contoso.local)、Enter キーを押します。
    
7. 予想される出力は、図に示す出力と同様である必要があります。 すべての DNS レコードがサンプル出力に表示されるわけではありませんが、すべてのレコードを検証する必要があることに注意してください。 
    
     ![DNS 設定を確認します。](../../media/4fcaa70f-7717-4939-9652-d2048d6293cc.png)
  

