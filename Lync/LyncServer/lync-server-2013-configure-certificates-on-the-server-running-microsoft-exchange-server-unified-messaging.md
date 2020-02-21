---
title: 'Lync Server 2013: Microsoft Exchange Server ユニファイドメッセージングを実行しているサーバーでの証明書の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure certificates on the server running Microsoft Exchange Server Unified Messaging
ms:assetid: 74c883b4-cef6-41a9-b2eb-7212be32fea4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398564(v=OCS.15)
ms:contentKeyID: 48184521
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 515be9190f9c5012dfd75cdda6621b7f4acfd88f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205086"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-certificates-on-the-server-running-microsoft-exchange-server-unified-messaging"></a>Microsoft Exchange Server ユニファイドメッセージングを実行しているサーバーで証明書を構成する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-09-26_

「計画」のドキュメントの「 [Lync Server 2013 での Exchange ユニファイドメッセージング統合の計画](lync-server-2013-planning-for-exchange-unified-messaging-integration.md)」で説明されているように、Exchange ユニファイドメッセージング (UM) を展開している場合、exchange um の機能を組織内のエンタープライズ voip ユーザーに提供するには、次の手順を使用して、exchange um を実行しているサーバーで証明書を

<div>


> [!IMPORTANT]  
> 内部証明書の場合、Lync Server 2013 を実行しているサーバーと Microsoft Exchange を実行しているサーバーの両方が、相互に信頼された信頼できるルート証明機関の証明書を持っている必要があります。 証明機関 (CA) は、サーバーが信頼されたルート証明機関の証明書ストアに登録されている証明機関のルート証明書を持っている限り、同一または別の証明機関にすることができます。



</div>

Lync Server 2013 に接続するためには、サーバー証明書を使用して Exchange サーバーを構成する必要があります。

1.  Exchange Server の CA 証明書をダウンロードします。

2.  Exchange Server の CA 証明書をインストールします。

3.  CA が、Exchange Server の信頼されたルート証明機関一覧にあることを確認します。

4.  Exchange Server の証明書要求を作成し、証明書をインストールします。

5.  Exchange Server の証明書を割り当てます。

<div>

## <a name="to-download-the-ca-certificate"></a>CA 証明書をダウンロードするには

1.  Exchange UM を実行しているサーバーで、[**スタート**] をクリックし、[**実行**] をクリックし**て、発行 CA サーバー\<\>の http://の名前**を入力し、[ **OK**] をクリックします。

2.  **[タスクの選択]** の **[CA 証明書、証明書チェーン、または CRL のダウンロード]** をクリックします。

3.  [ **Ca 証明書、証明書チェーン、または CRL のダウンロード**] の [ **Base 64 にエンコード方法**] を選択し、[ **ca 証明書のダウンロード**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > この手順では、識別エンコードルール (DER) エンコードを指定することもできます。 DER エンコードを選択する場合は、この手順の次のステップと「<STRONG>CA 証明書をインストールするには</STRONG>」のステップ 10 のファイル タイプが .cer ではなく、.p7b になります。

    
    </div>

4.  **[ファイルのダウンロード]** ダイアログ ボックスで **[保存]** をクリックし、ファイルをサーバー上のハード ディスクに保存します。(このファイルの拡張子は、前のステップで選択したエンコードに応じて、.cer または .p7b となります。)

</div>

<div>

## <a name="to-install-the-ca-certificate"></a>CA 証明書をインストールするには

1.  Exchange UM を実行しているサーバーで、[**スタート**] をクリックし、[**実行**] をクリックして、[**開く**] ボックスに「 **MMC** 」と入力し、[ **OK]** をクリックして、Microsoft 管理コンソール (MMC) を開きます。

2.  **[ファイル]** メニューの **[スナップインの追加と削除]** をクリックし、**[追加]** をクリックします。

3.  **[スタンドアロン スナップインの追加]** ボックスで、**[証明書]** をクリックし、**[追加]** をクリックします。

4.  **[証明書スナップイン]** ダイアログ ボックスの **[コンピューター アカウント]** をクリックし、**[次へ]** をクリックします。

5.  [**コンピューターの選択**] ダイアログボックスで、[**ローカルコンピューター: (このコンソールを実行しているコンピューター)** ] チェックボックスがオンになっていることを確認し、[**完了**] をクリックします。

6.  **[閉じる]** をクリックし、**[OK]** をクリックします。

7.  コンソール ツリーで、**[証明書 (ローカル コンピューター)]** を展開し、**[信頼されたルート証明機関]** を展開して **[証明書]** をクリックします。

8.  **[証明書]** を右クリックし、**[すべてのタスク]** をクリックして **[インポート]** をクリックします。

9.  **[次へ]** をクリックします。

10. **[参照]** をクリックしてファイルを特定し、**[次へ]** をクリックします。(このファイルの拡張子は、「**CA 証明書をダウンロードするには**」のステップ 3 で選択したエンコードに応じて、.cer または .p7b となります。)

11. **[証明書をすべて次のストアに配置する] **をクリックします。

12. **[参照]** をクリックし、**[信頼されたルート証明機関]** をクリックします。

13. **[次へ]** をクリックし、設定を確認して、**[完了]** をクリックします。

</div>

<div>

## <a name="to-verify-that-the-ca-is-in-the-list-of-trusted-root-cas"></a>CA が信頼されたルート証明機関の一覧にあることを確認するには

1.  Exchange UM を実行しているサーバーで、MMC の [**証明書 (ローカルコンピューター)**] を展開し、[**信頼されたルート証明機関**] を展開して、[**証明書**] をクリックします。

2.  詳細ウィンドウで、CA が、信頼されたルート証明機関の一覧にあることを確認します。

</div>

<div>

## <a name="to-configure-exchange-server-2013-um-with-lync-server"></a>Lync Server を使用して Exchange Server 2013 UM を構成するには

1.  詳細については、Exchange Server のドキュメントの「」の「Exchange 2013 UM と[https://go.microsoft.com/fwlink/p/?LinkId=265372](https://go.microsoft.com/fwlink/p/?linkid=265372)Lync Server の統合」を参照してください。

</div>

<div>

## <a name="to-create-a-certificate-request-and-install-the-certificate-on-exchange-server-2007-sp1"></a>証明書要求を作成して、証明書を Exchange Server 2007 (SP1) にインストールするには

1.  Exchange UM を実行しているサーバーで、[**スタート**] をクリックし、[**実行**] をクリックして、発行**\>CA サーバーの** **\<http://** の名前を入力し、[ **OK**] をクリックします。

2.  **[タスクの選択]** で **[証明書の要求]** をクリックします。

3.  **[証明書の要求]** で **[証明書の要求の詳細設定]** をクリックします。

4.  **[証明書の要求の詳細設定]** で **[この CA への要求を作成し送信する]** をクリックします。

5.  **[証明書の要求の詳細設定]** で、サーバー認証用に構成された **[Web サーバー]** 証明書テンプレートまたは別のサーバー証明書テンプレートを選択します。

6.  [**オフラインテンプレート用の識別情報**] の [**名前**] ボックスに、Exchange サーバーの完全修飾ドメイン名 (FQDN) を入力します。
    
    <div>
    

    > [!NOTE]  
    > 通信を可能にするには、Exchange Server の FQDN を入力する必要があります。

    
    </div>

7.  **[キーのオプション]** で **[ローカル コンピューターの証明書ストアに証明書を格納する]** チェック ボックスをオンにします。

8.  Web ページの下部にある **[送信]** をクリックします。

9.  確認のダイアログ ボックスで、**[はい]** をクリックします。

10. [証明書は発行されました] ページの **[証明書は発行されました]** で **[この証明書のインストール]** をクリックします。

11. 確認のダイアログ ボックスで、**[はい]** をクリックします。

12. "新しい証明書は正しくインストールされました" というメッセージが表示されることを確認します。

</div>

<div>

## <a name="to-create-a-certificate-on-exchange-server-2010"></a>Exchange Server 2010 で証明書を作成するには

1.  Exchange UM を実行しているサーバーに適切なユーザー権限を使用してログオンします。 詳細については、「」の「 [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499)クライアントアクセス許可」を参照してください。

2.  証明書を作成するには、以下の手順を参照してください。
    
    1.  「新しい Exchange 証明書を作成する」[https://go.microsoft.com/fwlink/p/?linkId=195494](https://go.microsoft.com/fwlink/p/?linkid=195494)
    
    2.  「Exchange 証明書をインポートする」[https://go.microsoft.com/fwlink/p/?linkId=195496](https://go.microsoft.com/fwlink/p/?linkid=195496)
    
    <div>
    

    > [!NOTE]  
    > 通信を可能にするには、証明書の <STRONG>[サブジェクト名]</STRONG> に、Exchange Server の FQDN を入力する必要があります。

    
    </div>

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2007-sp1"></a>Exchange Server 2007 (SP1) に証明書を割り当てるには

1.  Exchange UM を実行しているサーバーで、MMC を開きます。

2.  コンソール ツリーで **[個人]** を展開し、**[証明書]** をクリックします。

3.  詳細ウィンドウに個人の証明書が表示されていることを確認します。

4.  証明書をダブルクリックして詳細を表示し、有効になっていることを確認します。
    
    <div>
    

    > [!NOTE]  
    > 証明書に有効と表示されるまでに数分かかることがあります。

    
    </div>

5.  Microsoft Exchange ユニファイド メッセージング サービスを再開します。
    
    <div>
    

    > [!NOTE]  
    > Exchange Server 2007 SP1 ユニファイド メッセージングを実行しているサーバーで、正しい証明書が自動的に取得されます。

    
    </div>

6.  イベント ビューアを開き、イベント ID 1112 を探します。このイベントは、Exchange Server 2007 SP1 ユニファイド メッセージングを実行しているサーバーが取得した証明書を示します。

</div>

<div>

## <a name="to-assign-the-certificate-on-exchange-server-2010"></a>Exchange Server 2010 に証明書を割り当てるには

1.  Exchange UM を実行しているサーバーに適切なユーザー権限を使用してログオンします。 詳細については、「」の「 [https://go.microsoft.com/fwlink/p/?linkId=195499](https://go.microsoft.com/fwlink/p/?linkid=195499)クライアントアクセス許可」を参照してください。

2.  証明書を割り当てる手順については、「サービスを証明書に割り当てる[https://go.microsoft.com/fwlink/p/?linkId=195497](https://go.microsoft.com/fwlink/p/?linkid=195497)」を参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

