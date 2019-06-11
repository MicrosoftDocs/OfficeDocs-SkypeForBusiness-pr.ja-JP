---
title: 'Lync Server 2013: サーバーの証明書の構成'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure certificates for servers
ms:assetid: e12e59b5-a146-4859-86ec-cabfc198c7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398995(v=OCS.15)
ms:contentKeyID: 48185531
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 21a0e239074b4f6d4638214fad41ff8ba18078fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34840427"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-certificates-for-servers-in-lync-server-2013"></a>Lync Server 2013 でのサーバーの証明書の構成

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-03-17_

この手順を正常に完了するには、RTCUniversalServerAdmins グループのメンバーであるか、適切な権限が委任されているユーザーとしてログオンしている必要があります。 権限の委任の詳細については、「 [Lync Server 2013 でセットアップのアクセス許可を委任](lync-server-2013-delegate-setup-permissions.md)する」を参照してください。 組織によっては、証明書を要求するための要件によっては、他のグループメンバーシップが必要になる場合があります。 公開キー基盤 (PKI) 証明機関 (CA) を管理するグループと相談します。

<div>


> [!NOTE]  
> Lync Server 2013 には、Windows 7、Windows Server 512 R2、Windows Server 2008、Windows Vista、または windows Server 2008 を実行しているクライアントからの接続のダイジェストのハッシュと署名アルゴリズムが使用されています (SHA-1 は、224、256、384、またはビットのダイジェストの長さを使用します)。Lync Phone Edition に加えて、Windows XP オペレーティングシステム。 SHA-2 スイートを使用する外部アクセスをサポートするには、同じビット長のダイジェストを使用する証明書も発行できるパブリック CA が外部証明書を発行する必要があります。



</div>

<div>


> [!WARNING]  
> ハッシュ ダイジェストや署名アルゴリズムを選択するには、証明書を使用するクライアントやサーバー、そのクライアントやサーバーが通信するその他のコンピューターやデバイスに関する理解のほか、証明書で使用されるアルゴリズムの使用方法も把握する必要があります。 オペレーティングシステムと一部のクライアントアプリケーションでサポートされているダイジェストの長さについ<A href="http://go.microsoft.com/fwlink/?linkid=287002">http://go.microsoft.com/fwlink/?LinkId=287002</A>ては、「」を参照してください。



</div>

各標準エディションサーバーまたはフロントエンドサーバーには、oAuthTokenIssuer 証明書、既定の証明書、web 内部証明書、web 外部証明書の4つの証明書が必要です。 ただし、適切なサブジェクト代替名エントリと oAuthTokenIssuer 証明書の1つの既定の証明書を要求して割り当てることができます。 証明書の要件の詳細については、「 [Lync Server 2013 の内部サーバーの証明書要件](lync-server-2013-certificate-requirements-for-internal-servers.md)」を参照してください。 OAuthTokenIssuer 証明書の要求、割り当て、インストールの詳細については、「 [Lync server 2013 でサーバー間認証 (OAuth) とパートナーアプリケーションを管理する](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)」を参照してください。

Standard Edition server またはフロントエンドサーバー証明書を要求、割り当て、インストールするには、次の手順を使用します。 各フロントエンドサーバーに対して手順を繰り返します。

<div>


> [!IMPORTANT]  
> 次の手順では、組織によって展開された、またはオフライン要求処理を使用して、社内のエンタープライズ PKI から証明書を構成する方法について説明します。 パブリック CA から証明書を取得する方法については、計画ドキュメントの「 <A href="lync-server-2013-certificate-requirements-for-internal-servers.md">Lync Server 2013 の内部サーバーの証明書要件</A>」を参照してください。 また、この手順では、フロントエンドサーバーのセットアップ時に証明書を要求、割り当て、インストールする方法について説明します。 事前に証明書を要求した場合は、この展開ドキュメントの「 <A href="lync-server-2013-request-certificates-in-advance-optional.md">Lync Server 2013 について事前に証明書を要求する (オプション)</A> 」の説明に従ってください。または、組織内に展開された社内のエンタープライズ PKI を使って入手する必要はありません。証明書の場合は、必要に応じてこの手順を変更する必要があります。



</div>

<div>

## <a name="to-configure-certificates-for-a-front-end-server"></a>フロントエンドサーバー用の証明書を構成するには

1.  Lync Server 展開ウィザードで、[**手順 3: 証明書の要求、インストール、または割り当て**を行う] の横にある [**実行**] をクリックします。

2.  **証明書ウィザード**のページで [**要求**] をクリックします。

3.  [**証明書の要求**] ページで、[**次へ**] をクリックします。

4.  [**要求を後で送信または今すぐ送信**] ページで、[**次へ**] をクリックすることで、既定の [**要求をすぐにオンライン証明機関に送信する**] オプションを承諾できます。このオプションを選択した場合、自動オンライン登録による内部 CA を利用可能にする必要があります。要求延期オプションを選択すると、証明書の要求ファイルを保存するための名前と場所の入力を求められます。証明書の要求は、組織内の CA またはパブリック CA へ送信され、そこで処理される必要があります。要求者は証明書応答をインポートして、適切な証明書の役割に割り当てる必要があります。

5.  [**証明機関 (CA) の選択**] ページで、[**環境内で検出されたリストから ca を選択**する] オプションを選び、一覧から [Active Directory ドメインサービス (Active DIRECTORY Domain Services) ca への登録] を選びます。 または [**別の証明機関を指定してください**] をクリックして、ボックスに別の CA の名前を入力してから、[**次へ**] をクリックします。

6.  [**証明機関のアカウント**] ページで、CA に対する証明書要求の要求および処理のために、資格情報の入力を求められます。 証明書を要求するためには、ユーザー名とパスワードが必要かどうかを、事前に判断する必要があります。 CA 管理者には、必要な情報が含まれているため、この手順についてサポートが必要な場合があります。 別の資格情報の入力が必要な場合は、チェック ボックスをオンにして、テキスト ボックスにユーザー名とパスワードを入力してから、[**次へ**] をクリックします。

7.  [**代替証明書テンプレートの指定**] ページで、既定の Web サーバー テンプレートを使用する場合は [**次へ**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > CA の既定の Web サーバー テンプレートの代わりに使用するテンプレートを組織が作成している場合は、チェック ボックスをオンにして、代替テンプレートの名前を入力します。CA 管理者が定義したテンプレートの名前を入力する必要があります。

    
    </div>

8.  [**名前とセキュリティの設定**] ページで、証明書と目的を識別できる**フレンドリ名**を指定します。 空白のままにした場合、名前は自動的に生成されます。 キーの [**ビット長**] を設定するか、既定の 2048 ビットをそのまま使用します。 証明書と秘密キーを別のシステムに移動またはコピーする必要があると判断した場合は、[**証明書の秘密キーをエクスポート可能としてマークする**] をクリックして、[**次へ**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > Lync Server 2013 は、エクスポート可能な秘密キーの要件を最小限に抑えています。 その対象の 1 つがプール内のエッジ サーバーで、ここではメディア リレー認証サービスが、プール内の各インスタンスに対する個々の証明書ではなく、証明書のコピーを使用します。

    
    </div>

9.  [**組織情報**] ページで、必要に応じて組織情報を入力してから、[**次へ**] をクリックします。

10. [**地理情報**] ページで、必要に応じて地理情報を入力してから、[**次へ**] をクリックします。

11. [**サブジェクト名/サブジェクト代替名**] ページで、追加するサブジェクトの別名を確認してから、[**次へ**] をクリックします。

12. [**SIP ドメインの設定**] ページで、[**SIP ドメイン**] をクリックしてから、[**次へ**] をクリックします。

13. [**追加のサブジェクト代替名の構成**] ページで、追加する必須サブジェクトの別名 (今後追加する SIP ドメインで必要になる可能性がある名前を含む) を入力して、[**次へ**] をクリックします。

14. [**証明書要求の概要**] ページで、概要情報を確認します。情報が正しい場合には、[**次へ**] をクリックします。設定を修正または変更する必要がある場合には、[**戻る**] をクリックして、該当するページで修正または変更します。

15. [**コマンドを実行しています**] ページで、[**次へ**] をクリックします。

16. On the **Online Certificate Request Status** page, review the information returned. You should note that the certificate was issued and installed into the local certificate store. 発行およびインストールされているが有効ではないと報告される場合は、CA ルート証明書がサーバーの信頼済みルート CA ストアにインストールされていることを確認してください。 Refer to your CA documentation on how to retrieve a Trusted Root CA certificate. If you need to view the retrieved certificate, click **View Certificate Details**. 既定では、[**証明書を Lync Server 証明書の使用に割り当てる**] チェックボックスはオンになっています。 If you want to manually assign the certificate, clear the check box, and then click **Finish**.

17. 前のページで [**証明書を Lync Server 証明書の使用状況に割り当てる**] チェックボックスをオフにした場合は、[**証明書の割り当て**] ページが表示されます。 Click **Next**.

18. [**証明書ストア**] ページで、要求した証明書を選択します。証明書を表示するには、[**証明書の詳細の表示**] をクリックし、[**次へ**] をクリックして続行します。
    
    <div>
    

    > [!NOTE]  
    > [<STRONG>オンライン証明</STRONG>書の要求の状態] ページで証明書の問題 (証明書が有効ではないなど) が報告された場合は、実際の証明書を表示すると、問題の解決に役立ちます。 証明書が無効になる原因となる可能性のある特定の問題は、前に説明した信頼されていないルート CA 証明書と、証明書に関連付けられている秘密キーが見つからないことです。 この2つの問題を解決するには、CA のマニュアルを参照してください。

    
    </div>

19. [**証明書の割り当ての概要**] ページに表示された情報から、適切な証明書が割り当てられていることを確認して、[**次へ**] をクリックします。

20. [**コマンドの実行**] ページで、コマンドの出力を確認します。割り当てプロセスを確認する場合、またはエラーや警告が発行されたかどうかを確認する場合には、[**ログの表示**] をクリックします。確認を終了したら、[**終了**] をクリックします。

21. [**証明書ウィザード**] ページで、証明書の**状態**が [割り当て済み] であることを確認し、[**閉じる**] をクリックします。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の証明書インフラストラクチャの要件](lync-server-2013-certificate-infrastructure-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

