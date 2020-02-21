---
title: 明示的にサポートまたは制限されていないクライアントの既定のアクションを変更する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify the default action for clients not explicitly supported or restricted
ms:assetid: 548dd0f5-62fe-4c3f-8952-2b9fd4c5fff3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520994(v=OCS.15)
ms:contentKeyID: 48184137
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 87f2b88b43c41a5a8bf990a72f0fdfef1c5537e2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42184820"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="modify-the-default-action-for-clients-not-explicitly-supported-or-restricted-in-lync-server-2013"></a>Lync Server 2013 で明示的にサポートまたは制限されていないクライアントの既定のアクションを変更する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

Lync Server 2013 環境でサポートするクライアントのバージョンを指定することに加えて、バージョンポリシーが定義されていないクライアントの既定のアクションを指定することもできます。 これにより、Lync Server 環境で使用するクライアントバージョンを制限することができます。これは、複数のクライアントバージョンのサポートに関連するコストの制御に役立ちます。

<div>

## <a name="to-modify-the-default-action-for-clients-not-explicitly-supported-or-restricted"></a>明示的にサポートまたは制限されていないクライアントの既定のアクションを変更するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**クライアント**] をクリックし、[**クライアント バージョン構成**] をクリックします。

4.  [**クライアント バージョン構成**] ページで、リスト内の [**グローバル**] 構成をダブルクリックします。

5.  [**クライアント バージョン構成の編集**] ダイアログ ボックスで [**バージョン管理を有効にする**] チェック ボックスがオンになっていることを確認し、[**既定のアクション**] で次のいずれかを選択します。
    
      - **[許可**   ] クライアントバージョンが [**クライアントバージョンポリシー** ] リスト内のフィルターと一致しない場合に、クライアントのログオンを許可します。
    
      - **** クライアントバージョンが [**クライアントバージョンポリシー** ] リスト内のフィルターと一致しない場合に、クライアントのログオンを禁止します。   
    
      - **[Block in URL**   ] クライアントバージョンが [**クライアントバージョンポリシー** ] リスト内のフィルターと一致しない場合にクライアントのログオンを禁止し、新しいクライアントをダウンロードできる URL を含むエラーメッセージを含めます。
    
      - **Allow url**   を使用すると、クライアントのバージョンが [**クライアントバージョンポリシー** ] リスト内のフィルターと一致しない場合にクライアントがログオンでき、新しいクライアントをダウンロードできる URL を含むエラーメッセージが表示されます。

6.  [**禁止して URL を表示**] を選択した場合は、エラー メッセージに含めるクライアントのダウンロード用 URL を [**URL**] ボックスに入力します。

7.  [**確定**] をクリックします。

</div>

<div>

## <a name="to-disable-client-version-control"></a>クライアント バージョン管理を無効にするには

  - バージョン管理を無効にしてすべてのクライアントがクライアント バージョンに関係なくログオンできるようにするには、[**バージョン管理を有効にする**] をオフにして [**確定**] をクリックします。

</div>

<div>

## <a name="modifying-the-default-action-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用した既定のアクションの変更

ユーザーが明示的にサポートしていないクライアントまたはクライアントバージョンポリシーによって制限されていないクライアントを使用してユーザーがサインオンを試行したときに実行される既定のアクションは、Windows PowerShell コマンドラインインターフェイスおよび**Set-CsClientVersionPolicy**コマンドレットを使用して管理できます。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-configure-the-default-action-to-block-access"></a>アクセスをブロックする既定のアクションを構成するには

  - 次のコマンドでは、Redmond サイトの既定のアクションを "Block" に設定します。これにより、クライアント バージョン構成ルールが存在しないクライアントの登録が禁止されます。
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Block

</div>

<div>

## <a name="to-configure-the-default-action-to-allow-access"></a>アクセスを許可するように既定のアクションを構成するには

  - この例では、Redmond サイトの既定のアクションが "Allow" に設定されています。これにより、クライアント バージョン構成ルールが存在しないクライアントの登録が許可されます。
    
        Set-CsClientVersionConfiguration -Identity "site:Redmond" -DefaultAction Allow

</div>

詳細については、「 [Set-CsClientVersionPolicy](https://technet.microsoft.com/library/Gg398876(v=OCS.15)) 」コマンドレットのヘルプトピックを参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 でのデバイス、電話、クライアントアプリケーションの管理](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

