---
title: 併置した仲介サーバーをスタンドアロンの仲介サーバーに移行する (オプション)
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)
ms:assetid: 7c3c2fb4-4ff2-47b1-aab3-0aa91472eadb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205026(v=OCS.15)
ms:contentKeyID: 48184602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c49b75845bb9a673872c5f08225dd6e1c96b69a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34847942"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional"></a>併置した仲介サーバーをスタンドアロンの仲介サーバーに移行する (オプション)

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2012-10-19_

次の手順を使用して、標準エディションサーバーまたはフロントエンドプールに配置された仲介サーバーを、単一サイト展開用のスタンドアロンの仲介サーバーに移行します。

<div>

## <a name="to-transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server"></a>併置している仲介サーバーをスタンドアロンの仲介サーバーに移行するには

1.  トポロジビルダーから既存のトポロジを開きます。

2.  左側のウィンドウで、[**仲介プール**] に移動します。

3.  [**仲介プール**] を右クリックし、[**新しい仲介サーバー**] を選択します。

4.  [**新しい仲介プールの定義**] ページで、新しい仲介サーバープールの FQDN を指定します。 また、このプールを単一サーバープールにするか、複数サーバープールにするかを選択し、[**次へ**] をクリックします。

5.  新しい仲介サーバーが着信通話をルーティングする次ホップのフロントエンドサーバープールを選択し、[**次へ**] をクリックします。

6.  仲介サーバーで使用するエッジプールを選択し、[**次へ**] をクリックします。

7.  [ **Pstn ゲートウェイの指定**] ページで、前の pstn ゲートウェイを仲介サーバーに関連付けます。 ゲートウェイを選択し、[**追加**] をクリックします。

8.  [**完了**] をクリックして、[**新しい仲介プールの定義**] ウィザードを閉じます。

9.  [**トポロジビルダー**] で、トップノードの**Lync Server 2013**を選びます。

10. [**操作**] ウィンドウで、[**発行トポロジ**] を選択し、ウィザードを完了します。

11. 展開ドキュメントの[Lync server 2013 で、「仲介サーバー用のファイルをインストール](lync-server-2013-install-the-files-for-mediation-server.md)する」の手順に従って、新しい仲介サーバーにファイルをインストールします。

12. ファイルが仲介サーバーにインストールされたら、[トポロジビルダー] に戻り、左側のウィンドウでプールに移動します。

13. プールを右クリックして、[**プロパティの編集**] を選択します。

14. [**仲介サーバー**] で、[併置された**仲介サーバーを有効に**する] チェックボックスをオフにして、[ **OK]** をクリックします。

15. [**トポロジビルダー**] で、トップノードの**Lync Server 2013**を選びます。

16. [**アクション**] メニューで、[**トポロジの公開**] を選択し、ウィザードを完了します。

</div>

</div>

<span> </span>

</div>

</div>

</div>

