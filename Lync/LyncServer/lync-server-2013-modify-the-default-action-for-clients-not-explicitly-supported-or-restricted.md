---
title: 明示的にサポートまたは制限されていないクライアントの既定のアクションを変更する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify the default action for clients not explicitly supported or restricted
ms:assetid: 548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520994(v=OCS.15)
ms:contentKeyID: 48184137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97b364253a87f1cbff1ef60322c65780b6497880
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826844"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-action-for-clients-not-explicitly-supported-or-restricted-in-lync-server-2013"></a>Lync Server 2013 で明示的にサポートまたは制限されていないクライアントの既定のアクションを変更する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-23_

Lync Server 2013 環境でサポートするクライアントのバージョンを指定するだけでなく、バージョンポリシーが定義されていないクライアントに対する既定のアクションを指定することもできます。 これにより、Lync Server 環境で使用するクライアントバージョンを制限することができます。これにより、複数のクライアントバージョンのサポートに関連するコストを制御するのに役立ちます。

<div>

## <a name="to-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted"></a>明示的にサポートまたは制限されていないクライアントの既定のアクションを変更するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[**クライアント**] をクリックし、[**クライアントバージョンの構成**] をクリックします。

4.  [**クライアントバージョンの構成**] ページで、リスト内の**グローバル**構成をダブルクリックします。

5.  [**クライアントのバージョン構成の編集**] ダイアログボックスで、[**バージョン管理を有効に**する] チェックボックスがオンになっていることを確認し、[**既定のアクション**] で次のいずれかを選択します。
    
      - **[許可**   ] を選択すると、クライアントバージョンがクライアントの [**バージョンポリシー** ] 一覧のいずれのフィルターとも一致しない場合に、クライアントはログオンできます。
    
      - ****   クライアントのバージョンがクライアントの [**バージョンポリシー** ] の一覧のどのフィルターとも一致しない場合、ブロックされます。
    
      - **[Url**   を含むブロック] クライアントのバージョンが [**クライアントのバージョンポリシー** ] 一覧のいずれのフィルターとも一致しない場合、クライアントはログオンを拒否し、新しいクライアントをダウンロードできる url を含むエラーメッセージを含めます。
    
      - **[URL**   による許可] を使うと、クライアントのバージョンが [**クライアントのバージョンポリシー** ] のいずれのフィルターとも一致しない場合に、クライアントはログオンでき、新しいクライアントをダウンロードできる URL を含むエラーメッセージが表示されます。

6.  [ **Url でブロック**する] を選択した場合、[ **url** ] ボックスにエラーメッセージとして含めるクライアントのダウンロード URL を入力します。

7.  [**コミット**] をクリックします。

</div>

<div>

## <a name="to-disable-client-version-control"></a>クライアントのバージョン管理を無効にするには

  - クライアントのバージョンに関係なくすべてのクライアントがログオンできるバージョン管理を無効にするには、[**バージョン管理を有効**にする] チェックボックスをオフにして、[**コミット**] をクリックします。

</div>

<div>

## <a name="modifying-the-default-action-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して既定のアクションを変更する

クライアントバージョンポリシーによって明示的にサポートまたは制限されていないクライアントを使ってユーザーがサインインしようとしたときに実行される既定のアクションは、Windows PowerShell コマンドラインインターフェイスと**Set-CsClientVersionPolicy**コマンドレットを使用して管理できます。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。

<div>

## <a name="to-configure-the-default-action-to-block-access"></a>アクセスをブロックする既定のアクションを構成するには

  - 次のコマンドは、レドモンドサイトブロックの既定のアクションを設定します。 これにより、クライアントのバージョン設定ルールが存在しないクライアントについては、登録がブロックされます。
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Block

</div>

<div>

## <a name="to-configure-the-default-action-to-allow-access"></a>アクセスを許可するように既定のアクションを構成するには

  - この例では、Redmond サイトの既定のアクションが [許可] に設定されています。 これにより、クライアントのバージョン設定ルールが存在しないすべてのクライアントに対して登録が許可されます。
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Allow

</div>

詳細については、「 [Set-CsClientVersionPolicy](https://technet.microsoft.com/en-us/library/Gg398876(v=OCS.15)) 」コマンドレットのヘルプトピックを参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのデバイス、電話、クライアント アプリケーションの管理](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

