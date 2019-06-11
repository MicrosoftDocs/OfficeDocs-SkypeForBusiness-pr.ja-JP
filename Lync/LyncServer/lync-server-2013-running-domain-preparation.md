---
title: 'Lync Server 2013: ドメイン準備手続き'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Running domain preparation
ms:assetid: 95dab800-1f2c-4506-b36c-99986643b149
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398761(v=OCS.15)
ms:contentKeyID: 48184847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 16fdd01b15fe5858129300c3a9f2f26c3d3de672
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822280"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-domain-preparation-for-lync-server-2013"></a>Lync Server 2013 のドメイン準備手続き

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-04-16_

セットアップまたは Lync Server 管理シェルコマンドレットを使用して、ドメインを準備することができます。 ドメインを準備するコマンドレットでは、 **CsAdDomain を有効に**することができます。

ドメインの準備は、Lync Server 2013 用の Active Directory ドメインサービスの準備での最終的な手順です。

<div>

## <a name="to-use-setup-to-prepare-domains"></a>セットアップを使用してドメインを準備するには

1.  Domain Admins グループのメンバーとして、ドメイン内の任意のサーバーにログオンします。

2.  Lync Server 2013 のインストールフォルダーまたはメディアから setup.exe を実行して、Lync Server 展開ウィザードを開始します。

3.  [**Active Directory の準備**] をクリックして、展開状態が判別されるまで待ちます。

4.  [**手順 5: 現在のドメインの準備**] で、[**実行**] をクリックします。

5.  [**ドメインの準備**] ページで、[**次へ**] をクリックします。

6.  [**コマンドの実行**] ページで [**タスク状態: 完了**] を見つけて、[**ログの表示**] をクリックします。

7.  [**アクション**] 列で、[**ドメインの準備**] を展開し、各タスクの最後に** \<成功\> **の実行結果を探して、ドメインの準備が正常に完了したことを確認します。次に、[**完了**] をクリックします。

8.  Active Directory のレプリケーションが完了するのを待ちます。または、フォレストルートドメインコントローラーの [Active Directory サイトとサービス] スナップインで一覧表示されているすべてのドメインコントローラーへの複製が強制されます。

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-domain"></a>コマンドレットを使用してドメインを準備するには

1.  Domain Admins グループのメンバーとして、ドメイン内の任意のサーバーにログオンします。

2.  Lync Server のコアコンポーネントは、次のようにインストールします。
    
    1.  Lync Server 2013 のインストールフォルダーまたはメディアから setup.exe を実行して、Lync Server 展開ウィザードを開始します。
    
    2.  Microsoft Visual C++ 再頒布可能パッケージをインストールするかどうかを確認するメッセージが表示されたら、[**はい**] をクリックします。
    
    3.  [Lync Server 2013 セットアップ] ダイアログボックスで、Lync Server ファイルをインストールする場所を入力するように求められます。 既定の場所を選ぶか、目的の場所を**参照**し、[**インストール**] をクリックします。
    
    4.  [使用許諾契約] ページで、[**使用許諾契約書に同意**します] をオンにし、[ **OK]** をクリックします。 インストーラーは、Lync Server 2013 コアコンポーネントをインストールします。

3.  Lync Server 管理シェルを起動します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft Lync Server 2013**]、[ **lync server 管理シェル**] の順にクリックします。

4.  次のコマンドレットを実行します。
    
        Enable-CsAdDomain [-Domain <DomainFQDN>] 
    
    次に例を示します。
    
        Enable-CsAdDomain -Domain domain1.contoso.net 
    
    Domain パラメーターを指定しない場合、既定値はローカルドメインです。

5.  ドメインの準備が正常に完了したことを確認します。 次のコマンドレットを実行します。
    
        Get-CsAdDomain [-Domain <Domain FQDN>] [-DomainController <Domain controller FQDN>] [-GlobalCatalog <Global catalog server FQDN>] [-GlobalSettingsDomainController <Domain controller FQDN where global settings are stored>] 
    
    次に例を示します。
    
        Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
    
    <div>
    

    > [!NOTE]  
    > Parameter GlobalSettingsDomainController を使うと、グローバル設定が保存されている場所を指定できます。 設定がシステムコンテナーに保存されている場合 (つまり、グローバル設定が構成コンテナーに移行されていないアップグレード展開で一般的)、Active Directory フォレストのルートでドメインコントローラーを定義します。 グローバル設定を構成コンテナーに保存する (新しい展開または構成コンテナーに設定を移行しているアップグレードの展開で一般的) 場合、フォレストに任意のドメイン コントローラーを定義します。 このパラメーターを指定しない場合、設定は構成コンテナーに保存され、AD&nbsp;DS の任意のドメインコントローラーを参照することがコマンドレットによって想定されます。

    
    </div>
    
    **Domain**パラメーターを指定しない場合、既定値はローカルドメインです。
    
    このコマンドレットは、ドメインの準備が正常に完了した場合に、 **LC\_domainsettings\_状態\_** の値を返します。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 のコマンドレットの使用によるドメインの準備の無効化](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)  


[Lync Server 2013 のドメインの準備](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

