---
title: ユーザーの DNS レコードを作成Skype for Business Server
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
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 798a663c-0b63-4f75-b0a3-9c553cef8c5f
description: '概要: DNS を構成し、サーバーのインストール用に DNS レコードを作成する方法についてSkype for Business Server。 以下の Microsoft 評価センター Skype for Business Server無料試用版をダウンロードします https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server 。'
ms.openlocfilehash: 08a652f3ed2dd19d40aa1830ac91459d205b618a
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/30/2021
ms.locfileid: "58726326"
---
# <a name="create-dns-records-for-skype-for-business-server"></a>ユーザーの DNS レコードを作成Skype for Business Server
 
**概要:** DNS を構成し、サーバーのインストール用に DNS レコードを作成する方法についてSkype for Business Server。 以下の Microsoft 評価センター Skype for Business Server無料試用版をダウンロードします [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server) 。
  
正常Skype for Business Server機能するには、多数のドメイン ネーム システム (DNS) 設定を設定する必要があります。 これは、クライアントがサービスにアクセスする方法を知り、サーバーが互いについて知っているのです。 これらの設定は、DNS エントリを割り当てるとドメイン全体で使用できるので、展開ごとに 1 回だけ完了する必要があります。 手順 1 ~ 5 は、任意の順序で実行できます。 ただし、図に示されている手順 6、7、および 8 を順番に実行し、手順 1 ~ 5 の後に実行する必要があります。 DNS レコードの作成は、手順 5 ~ 8 で構成されます。 DNS の計画の詳細については、「環境要件 for [Skype for Business Server](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md) [2019」](../../../SfBServer2019/plan/system-requirements.md)を参照Skype for Business Serverしてください。
  
> [!IMPORTANT]
> これは、サーバー DNS 環境で DNS レコードを作成する方法の一例にWindows重要です。 Skype for Business Server には他にも多くの DNS エントリが必要であり、DNS レコードを作成する手順は、組織内の DNS を管理するために使用しているシステムによって異なります。 DNS の要件の完全な一覧については、「DNS の要件」を参照[Skype for Business Server。](../../plan-your-deployment/network-requirements/dns.md) 
  
![概要図。](../../media/d2fc733c-6a80-4d17-a02f-93b8c4bfb999.png)
  
## <a name="configure-dns"></a>DNS の構成

DNS レコードは、ユーザーがSkype for Business Server機能し、ユーザーがアクセスするために必要です。
  
この例では、pool.contoso.local という名前の DNS 負荷分散 FQDN を使用しています。 このプールは、3 台のサーバーで構成Skype for Business Server Enterprise Edition。 フロントエンド Standard Editionは、1 つのサーバーしか含めできません。 Standard Edition を使用すると、次の例に示すように、サーバーの DNS 負荷分散プールを作成する代わりに、フロントエンドの役割を参照するときに、単一の Standard Edition サーバーの完全修飾ドメイン名 (FQDN) のみを使用します。 フロントエンド ロールのみを使用するこの簡単な例には、次の表に DNS エントリが含まれています。 特定の DNS 要件を計画するには[、「DNS](../../plan-your-deployment/network-requirements/dns.md)の要件」を参照Skype for Business Server。 
  
 
|**説明**|**Record type**|**名前**|**解決先**|**負荷分散の種類**|
|:-----|:-----|:-----|:-----|:-----|
|内部 Web サービスの FQDN  <br/> |A  <br/> |webint.contoso.local  <br/> |内部 Web サービスの VIP  <br/> |サポートされているソフトウェアとハードウェア  <br/> |
|プールの FQDN  <br/> |A  <br/> |pool.contoso.local  <br/> |サーバー SFB01 の IP アドレス  <br/> |DNS  <br/> |
|SFB01 FQDN  <br/> |A  <br/> |SFB01.contoso.local  <br/> |サーバー SFB01 の IP アドレス  <br/> |DNS  <br/> |
|プールの FQDN  <br/> |A  <br/> |pool.contoso.local  <br/> |サーバー SFB02 の IP アドレス  <br/> |DNS  <br/> |
|SFB02 FQDN  <br/> |A  <br/> |SFB02.contoso.local  <br/> |サーバー SFB02 の IP アドレス  <br/> |DNS  <br/> |
|プールの FQDN  <br/> |A  <br/> |pool.contoso.local  <br/> |サーバー SFB03 の IP アドレス  <br/> |DNS  <br/> |
|SFB03 FQDN  <br/> |A  <br/> |SFB03.contoso.local  <br/> |サーバー SFB03 の IP アドレス  <br/> |DNS  <br/> |
|Skype for Business自動検出  <br/> |A  <br/> |lyncdiscoverinternal.contoso.local  <br/> |内部 Web サービスの VIP  <br/> |サポートされているソフトウェアとハードウェア  <br/> |
|会議の簡単な URL  <br/> |A  <br/> |meet.contoso.local  <br/> |内部 Web サービスの VIP  <br/> |サポートされているソフトウェアとハードウェア  <br/> |
|ダイヤルイン簡易 URL  <br/> |A  <br/> |dialin.contoso.local  <br/> |内部 Web サービスの VIP  <br/> |サポートされているソフトウェアとハードウェア  <br/> |
|Web スケジューラの簡単な URL  <br/> |A  <br/> |scheduler.contoso.local  <br/> |内部 Web サービスの VIP  <br/> |サポートされているソフトウェアとハードウェア  <br/> |
|管理簡易 URL  <br/> |A  <br/> |admin.contoso.local  <br/> |内部 Web サービスの VIP  <br/> |サポートされているソフトウェアとハードウェア  <br/> |
|従来の検出  <br/> |SRV  <br/> |_sipinternaltls._tcp.contoso.local  <br/> |プール FQDN (ポート 5061)  <br/> |該当なし  <br/> |
   
### <a name="create-dns-records"></a>DNS レコードの作成

1. DNS サーバーにログオンし、サーバー マネージャー **を開きます**。
    
2. [ツール] **ドロップダウン メニュー** をクリックし **、[DNS] をクリックします**。
    
3. SIP ドメインのコンソール ツリーで、[前方参照ゾーン] を展開し、インストールする SIP ドメインSkype for Business Server展開します。
    
4. 図に示すように、SIP ドメインを右クリックし、[ **新しいホスト (A または AAAA)]** を選択します。
    
     ![新しい A レコードを選択します。](../../media/f89c5c1f-b5b7-428c-a6e3-2bcd12e878c3.png)
  
5. [名前 **] ボックス** に、ホスト レコードの名前を入力します (ドメイン名は自動的に追加されます)。
    
6. **[IP アドレス**] ボックスに、個々のフロントエンド サーバーの IP アドレスを入力し、[関連付けられたポインター **(PTR)** レコードの作成] または [認証されたユーザーに同じ所有者名を持つ **DNS** レコードの更新を許可する] (該当する場合) を選択します。 これは、WEB サービスを除くすべてのトラフィックの負荷分散に DNS が使用されている前提に注意してください。 この例では、表に示すように、3 つのフロントエンド サーバーがあります。
    
   |**サーバー名**|**Type**|**Data**|
   |:-----|:-----|:-----|
   |SFB01  <br/> |ホスト (A)  <br/> |10.0.0.5  <br/> |
   |SFB02  <br/> |ホスト (A)  <br/> |10.0.0.6  <br/> |
   |SFB03  <br/> |ホスト (A)  <br/> |10.0.0.7  <br/> |
   
7. 次に、プールの DNS 負荷分散エントリを作成します。 DNS 負荷分散を使用すると、DNS は同じ DNS プール名を使用しながら、プール内の個々のサーバーに要求を送信できます。 DNS と負荷分散の詳細については、「DNS の要件」を参照[Skype for Business Server。](../../plan-your-deployment/network-requirements/dns.md) 
    
    > [!NOTE]
    > 複数のサーバーを一緒にプールする方法は、Enterprise Edition展開でのみ使用できます。 単一のサーバーまたは Enterprise サーバー Standard Editionする場合は、単一サーバーの A レコードのみを作成する必要があります。 
  
    たとえば、pool.contoso.local という名前のプールと 3 つのフロントエンド サーバーがある場合は、次の DNS エントリを作成します。
    
   |**FQDN**|**Type**|**Data**|
   |:-----|:-----|:-----|
   |pool.contoso.local  <br/> |ホスト (A)  <br/> |10.0.0.5  <br/> |
   |pool.contoso.local  <br/> |ホスト (A)  <br/> |10.0.0.6  <br/> |
   |pool.contoso.local  <br/> |ホスト (A)  <br/> |10.0.0.7  <br/> |
   
8. 計画された展開内のすべてのサーバーのレコードの作成を続行します。 
    
9. 従来の検出用のサービス レコード (SRV) レコードを作成するには、SIP ドメインを右クリックし、[その他の新しいレコード] **を選択します**。
    
10. [**リソース レコードの種類を選択**] の [**サービス ロケーション (SRV)**] をクリックし、[**レコードの作成**] をクリックします。
    
11. "**サービス**" フィールドをクリックし、「**_sipinternaltls**」と入力します。
    
12. "**プロトコル**" フィールドをクリックし、「**_tcp**」と入力します。
    
13. "**ポート番号**" フィールドをクリックし、「**5061**」と入力します。
    
14. [**このサービスを提供するホスト]** をクリックし、プールまたはサーバーの FQDN をStandard Editionします。
    
     ![新しいリソース レコード ダイアログのスクリーンショット。](../../media/54b1aac5-a2ec-41fe-90c0-02eaeaa9d1b4.png)
  
15. [**OK**] をクリックしてから、[**完了**] をクリックします。
    
### <a name="verify-dns-records"></a>DNS レコードを確認する

1. Authenticated Users グループのメンバーであるアカウントまたは同等のアクセス許可を持つアカウントを使用して、ドメインのクライアント コンピューターにログオンします。
    
2. [スタート **] ボタン** をクリックし **、「cmd」と入力** し、Enter キーを押します。
    
3. **nslookup \<FQDN of the Front End pool\> または** **\<FQDN of the Standard Edition server or single Enterprise Edition server\>** を入力し、Enter キーを押します。
    
4. 引き続き、展開の残りの A レコードを確認します。
    
5. レガシ クライアントをサポートし、SRV レコードを作成した場合は **、nslookup** プロンプトで **set type=srv** と入力して確認し、Enter キーを押します。
    
6. **「_sipinternaltls._tcp」と入力します。*domain***(たとえば、_sipinternaltls._tcp.contoso.local) をクリックし、Enter キーを押します。
    
7. 予想される出力は、図に示す出力と似ている必要があります。 すべての DNS レコードがサンプル出力に表示されるのではなく、すべてのレコードを確認する必要があります。 
    
     ![dns 設定を確認します。](../../media/4fcaa70f-7717-4939-9652-d2048d6293cc.png)
  

