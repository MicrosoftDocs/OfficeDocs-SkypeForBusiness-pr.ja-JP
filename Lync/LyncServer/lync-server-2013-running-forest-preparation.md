---
title: 'Lync Server 2013: フォレストの準備の実行'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running forest preparation
ms:assetid: 9d62f7be-bcfe-421d-8d8a-225567102a35
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412732(v=OCS.15)
ms:contentKeyID: 48184991
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8d9f0f1bc18cf7c0a54a5bacc9257e4264b7b93c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208463"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="running-forest-preparation-for-lync-server-2013"></a>Lync Server 2013 のフォレストの準備の実行

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2012-10-29_

セットアップまたは Lync Server 管理シェルコマンドレットを使用して、フォレストを準備することができます。 フォレストを準備するコマンドレットは **Enable-CsAdForest** です。

フォレストの準備が完了したら、ドメインの準備を実行する前に、グローバル設定がレプリケートされていることを確認する必要があります。

<div>

## <a name="to-use-setup-to-prepare-the-forest"></a>セットアップを使用してフォレストを準備するには

1.  ドメインに参加しているコンピューターに、フォレストのルート ドメインの Enterprise Admins グループのメンバーとしてログオンします。

2.  Lync Server 2013 インストールフォルダーまたはメディアから、setup.exe を実行して、展開ウィザードを開始します。

3.  [**Active Directory の準備**] をクリックし、展開状態が判別されるまで待ちます。

4.  [**ステップ 3: 現在のフォレストの準備**] で、[**実行**] をクリックします。

5.  [**フォレストの準備**] ページで、[**次へ**] をクリックします。
    
    <div>
    

    > [!NOTE]  
    > フォレストの準備 Lync Server 2013 のユニバーサルグループを配置する場所を選択できます。 組織の要件と一致する場所を選択します。

    
    </div>

6.  [**コマンドを実行しています**] ページで [**タスク状態: 完了**] を見つけて、[**ログの表示**] をクリックします。

7.  [**アクション**] 列の下にある [**フォレストの準備**] を展開し、各タスクの最後に** \<成功\> **した実行結果を検索して、フォレストの準備が正常に完了したことを確認し、ログを閉じて、[**完了**] をクリックします。

8.  Active Directory のレプリケーションが完了するまで待機するか、フォレストのルート ドメイン コントローラーの [**Active Directory サイトとサービス**] スナップインに一覧表示されているすべてのドメイン コントローラーへのレプリケーションを強制的に実行してから、ドメインの準備を実行します。サイト内でレプリケーションが数分以内に開始されるよう、すべての Active Directory サイト内のドメイン コントローラー間でレプリケーションを強制的に実行します。

</div>

<div>

## <a name="to-use-cmdlets-to-prepare-the-forest"></a>コマンドレットを使用してフォレストを準備するには

1.  ドメインに参加しているコンピューターに、フォレストのルート ドメインの Domain Admins グループ メンバーとしてログオンします。

2.  Lync Server コアコンポーネントを次のようにインストールします。
    
    1.  Lync Server 2013 のインストールフォルダーまたはメディアから、setup.exe を実行して Lync Server 展開ウィザードを起動します。
    
    2.  Microsoft Visual C++ (再頒布可能) のインストールを要求するメッセージが表示されたら、**[はい]** をクリックします。
    
    3.  [Lync Server 2013 セットアップ] ダイアログボックスで、Lync Server ファイルをインストールする場所を指定するように求められます。 既定の場所を選択するか、または好みの場所を **[参照]** で選択し、**[インストール]** をクリックします。
    
    4.  [使用許諾契約書] ページで **[使用許諾契約書に同意します]** チェック ボックスをオンにし、**[OK]** をクリックします。 インストーラーによって Lync Server 2013 のコアコンポーネントがインストールされます。

3.  Lync Server 管理シェルを以下の手順で起動します。[**スタート**]、[**すべてのプログラム**]、[**Microsoft Lync Server 2013**]、[**Lync Server 管理シェル**] の順にクリックします。

4.  実行
    
        Enable-CsAdForest [-GroupDomain <FQDN of the domain in which to create the universal groups>]
    
    次に例を示します。
    
        Enable-CsAdForest -GroupDomain domain1.contoso.com 
    
    GroupDomain パラメーターを指定しない場合、既定値はローカル ドメインになります。 以前に既定のドメインではないドメインでユニバーサル グループを作成した場合は、GroupDomain パラメーターを明示的に指定する必要があります。

5.  Active Directory のレプリケーションが完了するまで待機するか、フォレストのルート ドメイン コントローラーの [**Active Directory サイトとサービス**] スナップインに一覧表示されているすべてのドメイン コントローラーへのレプリケーションを強制的に実行してから、ドメインの準備を実行します。

6.  フォレストの準備が成功したことを確認します。次のコマンドレットを実行します。
    
        Get-CsAdForest 
    
    フォレストの準備が正常に完了した場合、このコマンドレットは**\_LC FORESTSETTINGS\_状態\_** の値を返します。

</div>

<div>

## <a name="see-also"></a>関連項目


[コマンドレットを使用して Lync Server 2013 のフォレストの準備を元に戻す](lync-server-2013-using-cmdlets-to-reverse-forest-preparation.md)  


[Lync Server 2013 のフォレストの準備](lync-server-2013-preparing-the-forest.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

