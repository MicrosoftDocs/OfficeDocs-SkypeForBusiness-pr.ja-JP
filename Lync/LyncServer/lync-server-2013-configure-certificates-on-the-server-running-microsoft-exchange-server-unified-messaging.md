---
title: 'Lync Server 2013: Microsoft Exchange Server ユニファイドメッセージングを実行しているサーバーで証明書を構成する'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure certificates on the server running Microsoft Exchange Server Unified Messaging
ms:assetid: 74c883b4-cef6-41a9-b2eb-7212be32fea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398564(v=OCS.15)
ms:contentKeyID: 48184521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfc9ed0f51b3f534d5967c7195cc39736a4ecae9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840412"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging"></a>Microsoft Exchange Server ユニファイドメッセージングを実行しているサーバーで証明書を構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-09-26_

「計画ドキュメントの[Lync Server 2013 での Exchange ユニファイドメッセージングの統合の計画](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)」の説明に従って、Exchange ユニファイドメッセージング (UM) を展開している場合、組織内のエンタープライズボイスユーザーに exchange UM 機能を提供する必要があります。組織では、次の手順を使用して、Exchange UM を実行しているサーバー上で証明書を構成することができます。

<div>


> [!IMPORTANT]  
> 内部証明書の場合、Lync Server 2013 を実行しているサーバーと、Microsoft Exchange を実行しているサーバーの両方が、相互に信頼されている信頼できるルート証明書を持っている必要があります。 証明機関 (CA) は、信頼されたルート機関の証明書ストアに証明機関のルート証明書が登録されている限り、同じまたは別の証明機関とすることができます。



</div>

Lync Server 2013 に接続するには、Exchange Server がサーバー証明書を使用して構成されている必要があります。

1.  Exchange サーバーの CA 証明書をダウンロードします。

2.  Exchange サーバーの CA 証明書をインストールします。

3.  CA が Exchange Server の信頼されているルート Ca のリストに含まれていることを確認します。

4.  Exchange Server の証明書要求を作成して、証明書をインストールします。

5.  Exchange Server の証明書を割り当てます。

<div>

## <a name="to-download-the-ca-certificate"></a>CA 証明書をダウンロードするには

1.  Exchange UM を実行しているサーバーで、[**スタート**] をクリックし、[**実行**] をクリックし**て、発行 CA サーバー\<\>の Http://の名前**を入力し、[ **OK]** をクリックします。

2.  [**タスクの選択**] で、[ **CA 証明書、証明書チェーン、または CRL をダウンロード**します] をクリックします。

3.  **Ca 証明書、証明書チェーン、または CRL**をダウンロード**するに**は、[エンコード方法] を [ベース 64] に、[ **ca 証明書のダウンロード**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > この手順では、識別エンコード規則 (DER) のエンコードを指定することもできます。 DER エンコードを選択した場合は、この手順の次の手順のファイルの種類と、 <STRONG>CA 証明書をインストールする</STRONG>手順10については .cer ではなく. p7b を使用します。

    
    </div>

4.  [**ファイルのダウンロード**] ダイアログボックスで、[**保存**] をクリックし、サーバーのハードディスクにファイルを保存します。 (前の手順で選んだエンコードに応じて、ファイル拡張子は .cer または. p7b のいずれかになります)。

</div>

<div>

## <a name="to-install-the-ca-certificate"></a>CA 証明書をインストールするには

1.  Exchange UM を実行しているサーバーで、[**スタート**]、[実行]、[**名前**を指定**** して**実行**] の順にクリックし、[ **OK**] をクリックして、Microsoft 管理コンソール (mmc) を開きます。

2.  [**ファイル**] メニューで、[スナップインの**追加と削除**] をクリックし、[**追加**] をクリックします。

3.  [**スタンドアロンスナップ**インの追加] ボックスで、[**証明書**] をクリックし、[**追加**] をクリックします。

4.  [**証明書スナップイン**] ダイアログ ボックスの [**コンピューター アカウント**] をクリックし、[**次へ**] をクリックします。

5.  **[コンピューターの選択**] ダイアログボックスで、[**ローカルコンピューター: (このコンソールが実行されているコンピューター)** ] チェックボックスがオンになっていることを確認し、[**完了**] をクリックします。

6.  [**閉じる**] をクリックし、[ **OK**] をクリックします。

7.  コンソールツリーで、[**証明書 (ローカルコンピューター)**]、[**信頼されたルート証明機関**] の順に展開し、[**証明書**] をクリックします。

8.  [**証明書**] を右クリックし、[**すべてのタスク**] をクリックして、[**インポート**] をクリックします。

9.  [ **次へ**] をクリックします。

10. [**参照**] をクリックしてファイルを指定し、[**次へ**] をクリックします。 (手順3で選択したエンコード方法によって、 **CA 証明書をダウンロードする**場合は、.cer または. p7b のファイル拡張子のいずれかが表示されます。

11. [**証明書をすべて次のストアに配置する] を**クリックします。

12. [**参照**] をクリックし、[**信頼されたルート証明機関**] を選びます。

13. [**次へ**] をクリックして設定を確認し、[**完了**] をクリックします。

</div>

<div>

## <a name="to-verify-that-the-ca-is-in-the-list-of-trusted-root-cas"></a>CA が信頼されたルート Ca のリストに含まれていることを確認するには

1.  Exchange UM を実行しているサーバーで、MMC で [**証明書 (ローカルコンピューター)**]、[**信頼されたルート証明機関**] の順に展開し、[**証明書**] をクリックします。

2.  [詳細] ウィンドウで、CA が信頼できる Ca の一覧にあることを確認します。

</div>

<div>

## <a name="to-configure-exchange-server-2013-um-with-lync-server"></a>Exchange Server 2013 UM を Lync Server と共に構成するには

1.  詳細については、Exchange Server のドキュメントの「Exchange 2013 UM と Lync Server の[http://go.microsoft.com/fwlink/p/?LinkId=265372](http://go.microsoft.com/fwlink/p/?linkid=265372)統合」を参照してください。

</div>

<div>

## <a name="to-create-a-certificate-request-and-install-the-certificate-on-exchange-server-2007-sp1"></a>証明書の要求を作成し、Exchange Server 2007 (SP1) で証明書をインストールするには

1.  Exchange UM を実行しているサーバーで、[**スタート**] をクリックし、[**実行**] を**\>** クリックして、発行 CA サーバーの**\<http://** の名前を入力し、[ **OK]** をクリックします。

2.  [**タスクの選択**] の [**証明書の要求**] をクリックします。

3.  [**証明書の要求**] で [**証明書の要求の詳細設定**] をクリックします。

4.  [ **Advanced Certificate request**] の下で、[**作成してこの CA に要求を送信**] をクリックします。

5.  [ **Advanced Certificate Request**] で、[ **Web サーバー**またはサーバー認証用に構成された別のサーバー証明書テンプレート] を選択します。

6.  [**オフラインテンプレートの識別情報**] の [**名前**] ボックスに、Exchange サーバーの完全修飾ドメイン名 (FQDN) を入力します。
    
    <div>
    

    > [!NOTE]  
    > 通信を機能させるには、Exchange Server の FQDN を入力する必要があります。

    
    </div>

7.  [**キーのオプション**] で、[**ローカルコンピューターの証明書ストアに証明書を格納**する] チェックボックスをオンにします。

8.  Web ページの下部にある [**送信**] ボタンをクリックします。

9.  確認を求めるダイアログボックスが表示されたら、[**はい**] をクリックします。

10. [発行された証明書] ページで、[**証明書の発行**] の [**この証明書のインストール**] をクリックします。

11. 確認を求めるダイアログボックスが表示されたら、[**はい**] をクリックします。

12. "新しい証明書が正常にインストールされました。" というメッセージが表示されていることを確認します。

</div>

<div>

## <a name="to-create-a-certificate-on-exchange-server-2010"></a>Exchange Server 2010 で証明書を作成するには

1.  適切なユーザー権限を持つ Exchange UM を実行しているサーバーにログオンします。 詳細については、の「クライアントアクセス[http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499)許可」を参照してください。

2.  証明書を作成するには、次の手順を参照してください。
    
    1.  "新しい Exchange 証明書を作成する"[http://go.microsoft.com/fwlink/p/?linkId=195494](http://go.microsoft.com/fwlink/p/?linkid=195494)
    
    2.  "Exchange 証明書をインポートする"[http://go.microsoft.com/fwlink/p/?linkId=195496](http://go.microsoft.com/fwlink/p/?linkid=195496)
    
    <div>
    

    > [!NOTE]  
    > 証明書の<STRONG>サブジェクト名</STRONG>については、通信を機能させるために Exchange SERVER の FQDN を入力する必要があります。

    
    </div>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2007-sp1"></a>Exchange Server 2007 (SP1) で証明書を割り当てるには

1.  Exchange UM を実行しているサーバーで、MMC を開きます。

2.  コンソールツリーで、[**個人**] を展開し、[**証明書**] をクリックします。

3.  [詳細] ウィンドウで、[個人証明書] が表示されていることを確認します。

4.  証明書をダブルクリックして詳細を確認し、それが有効であることを確認します。
    
    <div>
    

    > [!NOTE]  
    > 証明書が有効として表示されるまでに数分かかることがあります。

    
    </div>

5.  Microsoft Exchange ユニファイドメッセージングサービスを再起動します。
    
    <div>
    

    > [!NOTE]  
    > Exchange Server 2007 SP1 ユニファイドメッセージングを実行しているサーバーでは、適切な証明書が自動的に取得されます。

    
    </div>

6.  イベントビューアーを開き、イベント ID 1112 を探します。これにより、Exchange Server 2007 SP1 ユニファイドメッセージングが実行されているサーバーがどの証明書を取得したかが指定されます。

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2010"></a>Exchange Server 2010 で証明書を割り当てるには

1.  適切なユーザー権限を持つ Exchange UM を実行しているサーバーにログオンします。 詳細については、の「クライアントアクセス[http://go.microsoft.com/fwlink/p/?linkId=195499](http://go.microsoft.com/fwlink/p/?linkid=195499)許可」を参照してください。

2.  証明書を割り当てる手順については、の「証明書にサービスを[http://go.microsoft.com/fwlink/p/?linkId=195497](http://go.microsoft.com/fwlink/p/?linkid=195497)割り当てる」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

