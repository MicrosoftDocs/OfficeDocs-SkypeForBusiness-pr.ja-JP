---
title: 'Lync Server 2013: ドメインの準備の実行'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running domain preparation
ms:assetid: 95dab800-1f2c-4506-b36c-99986643b149
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398761(v=OCS.15)
ms:contentKeyID: 48184847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d22c35f4e1a2b117ffa765446a94c9a7d2b0fd0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201163"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="running-domain-preparation-for-lync-server-2013"></a>Lync Server 2013 のドメインの準備を実行する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-04-16_

セットアップまたは Lync Server 管理シェルコマンドレットを使用して、ドメインを準備することができます。 ドメインを準備するコマンドレットは、 **-CsAdDomain を有効に**します。

「ドメインの準備」は、Lync Server 2013 用の Active Directory ドメインサービスを準備するための最後の手順です。

<div>

## <a name="to-use-setup-to-prepare-domains"></a>セットアップを使用してドメインを準備するには

1.  Domain Admins グループのメンバーとしてドメイン内の任意のサーバーにログオンします。

2.  Lync Server 2013 のインストールフォルダーまたはメディアから、setup.exe を実行して Lync Server 展開ウィザードを起動します。

3.  [**Active Directory の準備**] をクリックし、展開状態が判別されるまで待ちます。

4.  [**手順 5: 現在のドメインの準備**] で、[**実行**] をクリックします。

5.  [**ドメインの準備**] ページで、[**次へ**] をクリックします。

6.  [**コマンドを実行しています**] ページで [**タスク状態: 完了**] を見つけて、[**ログの表示**] をクリックします。

7.  [**アクション**] 列の下にある [**ドメインの準備**] を展開し、各タスクの最後に** \<成功\> **した実行結果を検索して、ドメインの準備が正常に完了したことを確認し、ログを閉じて、[**完了**] をクリックします。

8.  Active Directory のレプリケーションが完了するまで待機するか、フォレストのルートドメインコントローラーの [Active Directory サイトとサービス] スナップインに一覧表示されているすべてのドメインコントローラーへのレプリケーションを強制的に実行します。

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-domain"></a>コマンドレットを使用してドメインを準備するには

1.  Domain Admins グループのメンバーとしてドメイン内の任意のサーバーにログオンします。

2.  Lync Server コアコンポーネントを次のようにインストールします。
    
    1.  Lync Server 2013 のインストールフォルダーまたはメディアから、setup.exe を実行して Lync Server 展開ウィザードを起動します。
    
    2.  Microsoft Visual C++ (再頒布可能) のインストールを要求するメッセージが表示されたら、**[はい]** をクリックします。
    
    3.  [Lync Server 2013 セットアップ] ダイアログボックスで、Lync Server ファイルをインストールする場所を指定するように求められます。 既定の場所を選択するか、または好みの場所を **[参照]** で選択し、**[インストール]** をクリックします。
    
    4.  [使用許諾契約書] ページで **[使用許諾契約書に同意します]** チェック ボックスをオンにし、**[OK]** をクリックします。 インストーラーによって Lync Server 2013 のコアコンポーネントがインストールされます。

3.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

4.  実行
    
        Enable-CsAdDomain [-Domain <DomainFQDN>] 
    
    次にその例を示します。
    
        Enable-CsAdDomain -Domain domain1.contoso.net 
    
    ドメイン パラメーターを指定しない場合、既定はローカル ドメインです。

5.  ドメインの準備が成功したことを確認します。 実行
    
        Get-CsAdDomain [-Domain <Domain FQDN>] [-DomainController <Domain controller FQDN>] [-GlobalCatalog <Global catalog server FQDN>] [-GlobalSettingsDomainController <Domain controller FQDN where global settings are stored>] 
    
    次に例を示します。
    
        Get-CsAdDomain -Domain domain1.contoso.net -GlobalSettingsDomainController dc01.domain1.contoso.com
    
    <div>
    

    > [!NOTE]  
    > パラメーター GlobalSettingsDomainController を使用して、グローバル設定を保存する場所を指定できます。 設定がシステムコンテナーに格納されている場合 (これは、構成コンテナーにグローバル設定が移行されていないアップグレード展開で一般的に使用されます)、Active Directory フォレストのルートにドメインコントローラーを定義します。 グローバル設定を構成コンテナーに保存する (新しい展開または構成コンテナーに設定を移行しているアップグレードの展開で一般的) 場合、フォレストに任意のドメイン コントローラーを定義します。 このパラメーターを指定しない場合、コマンドレットは、設定が構成コンテナーに格納されていると見なし、AD&nbsp;DS の任意のドメインコントローラーを参照します。

    
    </div>
    
    **Domain**パラメーターを指定しない場合、既定値はローカルドメインになります。
    
    このコマンドレットは、ドメインの準備が正常に完了した場合に、 **LC\_domainsettings\_状態\_** の値を返します。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 のコマンドレットを使用してドメインの準備を元に戻す](lync-server-2013-using-cmdlets-to-reverse-domain-preparation.md)  


[Lync Server 2013 のドメインの準備](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

