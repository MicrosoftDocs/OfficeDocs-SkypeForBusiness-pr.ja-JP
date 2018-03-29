---
title: Skype for Business Server 2015 での DNS レコードの作成
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 798a663c-0b63-4f75-b0a3-9c553cef8c5f
description: '概要: は、DNS を構成し、ビジネス サーバー 2015 の Skype のインストール用の DNS レコードを作成する方法を説明します。 マイクロソフト評価センターからのビジネス サーバー 2015 の Skype の無料試用版をダウンロード: https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server。'
ms.openlocfilehash: 4a8374c76995a0a42aad58b54aa0d567514d07de
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/28/2018
---
# <a name="create-dns-records-for-skype-for-business-server-2015"></a>Skype for Business Server 2015 での DNS レコードの作成
 
**の概要:**DNS を構成し、ビジネス サーバー 2015 の Skype のインストール用の DNS レコードを作成する方法について説明します。 マイクロソフト評価センターからのビジネス サーバー 2015 の Skype の無料試用版をダウンロード: [https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server](https://www.microsoft.com/evalcenter/evaluate-skype-for-business-server)。
  
正常に動作するサーバーをビジネスの Skype は、いくつかのドメイン ネーム システム (DNS) 設定の必要があります。 これは、クライアントがサービスにアクセスする方法を認識し、サーバーが相互を認識するようにするためです。 ユーザーが DNS エントリを割り当てればドメイン全体で使用できるようになるため、これらの設定を完了する必要があるのは、展開ごとに 1 回だけです。 手順 1 ～ 5 は任意の順序で実行できます。 ただし、手順 6、7、および 8 は、手順 1 ～ 5 の後に、図の順序で実行する必要があります。 DNS レコードの作成は、8 つの手順のうちの 5 番目です。 DNS の計画についての詳細については、 [Skype のビジネス サーバー 2015 の環境の要件](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)を参照してください。
  
> [!IMPORTANT]
> これは、Windows サーバーの DNS 環境で DNS レコードを作成する方法の例では同様に重要です。 ビジネス サーバーでは、Skype に必要なその他の多くの DNS エントリがあるし、DNS レコードを作成する手順は、組織内の DNS を管理するために使用しているシステムによって異なります。 DNS の要件の一覧は、[ビジネス サーバー 2015 の Skype の DNS の要件](../../plan-your-deployment/network-requirements/dns.md)を参照してください。 
  
![概要図](../../media/d2fc733c-6a80-4d17-a02f-93b8c4bfb999.png)
  
## <a name="configure-dns"></a>DNS の構成

DNS レコードは、Skype ビジネス サーバーで正常に動作し、ユーザーがアクセスできる必要があります。
  
この例では、DNS 負荷分散される、pool.contoso.local という名前の FQDN を使用しています。 このプールは、Skype ビジネス サーバー 2015 の Enterprise Edition を実行している 3 つのサーバーで構成されています。 1 台の Standard Edition フロントエンド サーバーに搭載できるサーバーは 1 台のみです。 この例のように、DNS 負荷分散されるサーバー プールを作成するのではなくフロントエンドの役割を参照する場合、Standard Edition を使用することで、1 台の Standard Edition サーバーの完全修飾ドメイン名 (FQDN) のみを使用することになります。 フロントエンドの役割のみを使用するこのシンプルな例には、次の表の DNS エントリが含まれます。 特定の DNS の要件を計画するには、[ビジネス サーバー 2015 の Skype の DNS の要件](../../plan-your-deployment/network-requirements/dns.md)を参照してください。 
  
 
|**説明**|**レコードの種類**|**名**|**解決します。**|**負荷分散の種類**|
|:-----|:-----|:-----|:-----|:-----|
|内部 Web サービスの FQDN  <br/> |A  <br/> |webint.contoso.local  <br/> |内部 Web サービスの VIP  <br/> |サポートされるソフトウェアとハードウェア  <br/> |
|プールの FQDN  <br/> |A  <br/> |pool.contoso.local  <br/> |サーバー SFB01 の IP アドレス  <br/> |DNS  <br/> |
|SFB01 の FQDN  <br/> |A  <br/> |SFB01.contoso.local  <br/> |サーバー SFB01 の IP アドレス  <br/> |DNS  <br/> |
|プールの FQDN  <br/> |A  <br/> |pool.contoso.local  <br/> |サーバー SFB02 の IP アドレス  <br/> |DNS  <br/> |
|SFB02 の FQDN  <br/> |A  <br/> |SFB02.contoso.local  <br/> |サーバー SFB02 の IP アドレス  <br/> |DNS  <br/> |
|プールの FQDN  <br/> |A  <br/> |pool.contoso.local  <br/> |サーバー SFB03 の IP アドレス  <br/> |DNS  <br/> |
|SFB03 の FQDN  <br/> |A  <br/> |SFB03.contoso.local  <br/> |サーバー SFB03 の IP アドレス  <br/> |DNS  <br/> |
|Skype for Business の自動検出  <br/> |A  <br/> |lyncdiscoverinternal.contoso.local  <br/> |内部 Web サービスの VIP  <br/> |サポートされるソフトウェアとハードウェア  <br/> |
|会議の簡易 URL  <br/> |A  <br/> |meet.contoso.local  <br/> |内部 Web サービスの VIP  <br/> |サポートされるソフトウェアとハードウェア  <br/> |
|ダイヤルインの簡易 URL  <br/> |A  <br/> |dialin.contoso.local  <br/> |内部 Web サービスの VIP  <br/> |サポートされるソフトウェアとハードウェア  <br/> |
|Web Scheduler の簡易 URL  <br/> |A  <br/> |scheduler.contoso.local  <br/> |内部 Web サービスの VIP  <br/> |サポートされるソフトウェアとハードウェア  <br/> |
|管理の簡易 URL  <br/> |A  <br/> |admin.contoso.local  <br/> |内部 Web サービスの VIP  <br/> |サポートされるソフトウェアとハードウェア  <br/> |
|従来の検出  <br/> |SRV  <br/> |_sipinternaltls._tcp.contoso.local  <br/> |プールの FQDN (ポート 5061)  <br/> |該当なし  <br/> |
   
### <a name="create-dns-records"></a>DNS レコードの作成

1. DNS サーバーにログオンして、[**サーバー マネージャー**] を開きます。
    
2. [**ツール**] ドロップダウン メニューをクリックし、[**DNS**] をクリックします。
    
3. SIP ドメインのコンソール ツリーで**[前方参照ゾーン**] を展開し、ビジネス サーバー用の Skype をインストールする SIP ドメインを展開し、します。
    
4. 図のように、SIP ドメインを右クリックして、[**新しいホスト (A または AAAA)**] を選択します。
    
     ![新規 A レコードの選択](../../media/f89c5c1f-b5b7-428c-a6e3-2bcd12e878c3.png)
  
5. [**名前**] ボックスにホスト レコード名を入力します (ドメイン名は自動的に追加されます)。
    
6. [**IP アドレス**] ボックスで、個々のフロントエンド サーバーの IP アドレスを入力し、適用可能な場合は [**関連付けられたポインター (PTR) レコードを作成する**] または [**同じ所有者名の DNS レコードの更新を認証されたユーザーに許可する**] を選択します。ここでは、Web サービスを除き、すべてのトラフィックの負荷分散に DNS が使用されると想定されています。この例では、表に示すように、3 台のフロントエンド サーバーがあります。
    
   |**サーバー名**|**タイプ**|**データ**|
   |:-----|:-----|:-----|
   |SFB01  <br/> |ホスト (A)  <br/> |10.0.0.5 に対し  <br/> |
   |SFB02  <br/> |ホスト (A)  <br/> |10.0.0.6  <br/> |
   |SFB03  <br/> |ホスト (A)  <br/> |10.0.0.7  <br/> |
   
7. 次に、プールの DNS 負荷分散のエントリを作成します。 DNS 負荷分散により、同じ DNS プール名を使用しながら、DNS ではプールの個別のサーバーに要求を送信することができます。 DNS および負荷分散に関する詳細については、 [Skype のビジネス サーバー 2015 の DNS の要件](../../plan-your-deployment/network-requirements/dns.md)を参照してください。 
    
    > [!NOTE]
    > 複数のサーバーをまとめてプールにする操作は、Enterprise Edition 展開でのみ使用できます。Enterprise Server または Standard Edition サーバーを 1 台展開している場合は、その 1 台のサーバー用の A レコードのみを作成する必要があります。 
  
    たとえば、pool.contoso.local という名前のプールと 3 台のフロントエンド サーバーがある場合は、次の DNS エントリを作成します。
    
   |**FQDN**|**タイプ**|**データ**|
   |:-----|:-----|:-----|
   |pool.contoso.local  <br/> |ホスト (A)  <br/> |10.0.0.5 に対し  <br/> |
   |pool.contoso.local  <br/> |ホスト (A)  <br/> |10.0.0.6  <br/> |
   |pool.contoso.local  <br/> |ホスト (A)  <br/> |10.0.0.7  <br/> |
   
8. 計画済みの展開に含まれるすべてのサーバー用の A レコードの作成を続行します。 
    
9. 従来の検出用のサービス レコード (SRV) を作成するには、SIP ドメインを右クリックして、[**その他の新しいレコード**] を選択します。
    
10. [**リソース レコードの種類を選択**] の [**サービス ロケーション (SRV)**] をクリックし、[**レコードの作成**] をクリックします。
    
11. [**サービス**] をクリックし、「**_sipinternaltls**」と入力します。
    
12. [**プロトコル**] をクリックし、「**_tcp**」と入力します。
    
13. [**ポート番号**] をクリックし、「**5061**」と入力します。
    
14. [**このサービスを提供しているホスト**] をクリックして、プールまたは Standard Edition サーバーの FQDN を入力します。
    
     ![新規リソース レコード ダイアログのスクリーンショット](../../media/54b1aac5-a2ec-41fe-90c0-02eaeaa9d1b4.png)
  
15. [**OK**] をクリックしてから、[**完了**] をクリックします。
    
### <a name="verify-dns-records"></a>DNS レコードの確認

1. Authenticated Users グループのメンバーであるアカウントまたは同等のアクセス許可を持つアカウントを使用して、ドメインのクライアント コンピューターにログオンします。
    
2. [**スタート**] ボタンをクリックし、「**cmd**」と入力して、Enter キーを押します。
    
3. 型**nslookup\<フロント エンド プールの FQDN\>**または**\<Standard Edition サーバーまたは Enterprise Edition の 1 つのサーバーの FQDN\>**、し、Enter キーを押します。
    
4. 引き続き、展開の残りの A レコードを確認します。
    
5. 従来のクライアントをサポートしていて、SRV レコードの作成が完了している場合は、**nslookup** プロンプトで「**set type=srv**」と入力して、Enter キーを押します。
    
6. タイプ * * _sipinternaltls._tcp。 *ドメイン** * (_sipinternaltls._tcp.contoso.local など)、し、Enter キーを押します。
    
7. 想定される出力は、図に示す出力のようになります。サンプル出力にはすべての DNS レコードが表示されているわけではありませんが、すべてのレコードを確認する必要があります。 
    
     ![DNS 設定を確認します。](../../media/4fcaa70f-7717-4939-9652-d2048d6293cc.png)
  

