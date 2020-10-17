---
title: Lync Phone Edition 構成設定のコレクションを作成または変更する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of Lync Phone Edition configuration settings
ms:assetid: 6cf714af-8f57-4a71-89ad-0a776302b2ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688086(v=OCS.15)
ms:contentKeyID: 49733683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11e2d314497223b5a18aa864b0e5333e3762480d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506214"
---
# <a name="create-or-modify-a-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a>Lync Server 2013 の Lync Phone Edition 構成設定のコレクションを作成または変更する

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

Lync Server をインストールすると、Lync Phone Edition 設定のグローバルコレクションが取得されます。 これらの設定は、展開で Lync Phone Edition を実行しているすべてのデバイスに適用されます。 これらの設定はいつでも変更できます。 また、特定のサイト内のデバイスに適用される新しい設定のコレクションを設定することもできます。 サイト設定はグローバル設定よりも優先されます。

構成設定は、コレクション名、スコープ (グローバルまたはサイト)、SIP セキュリティ設定、ログ レベル、音声のサービス品質 (QoS) レベル、電話のロックの設定、および電話のロックの詳細 (暗証番号 (PIN) を解除する必要がある期間と、電話が自動的にロックされる前に電話がアイドル状態になる期間) で構成されます。

<div>

## <a name="to-create-a-collection-of-lync-phone-edition-configuration-settings-or-edit-settings-for-an-existing-collection"></a>Lync Phone Edition の構成設定のコレクションを作成するか、既存のコレクションの設定を編集するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザー ウィンドウを開いて管理 URL を入力し、Lync Server コントロール パネルを開きます。 Lync Server コントロールパネルの起動に使用できるさまざまな方法の詳細については、「 [Open Lync server 2013 管理ツール](lync-server-2013-open-lync-server-administrative-tools.md)」を参照してください。

3.  左側のナビゲーション バーで [**クライアント**] をクリックし、[**デバイス構成**] ナビゲーション ボタンをクリックします。

4.  [**デバイス構成**] ページで、次のいずれかを実行します。
    
      - Lync Phone Edition 構成設定の新しいコレクションを作成するには、[ **新規**] をクリックし、サイトを選択して [ **OK**] をクリックし、既定の設定を確認し、必要に応じて変更を加えます。
    
      - 既存のコレクションの設定を変更するには、コレクションをクリックし、[**編集**] メニューをクリックします。[**詳細の表示**] をクリックし、変更を行います。
        
        <div>
        

        > [!TIP]
        > グローバル コレクションの既定の設定に戻すには、[<STRONG>編集</STRONG>] メニューをクリックして [<STRONG>削除</STRONG>] をクリックし、[<STRONG>OK</STRONG>] をクリックします。この操作では、グローバル コレクションが削除されるのではなく、設定が既定にリセットされるだけです。

        
        </div>

5.  [**コミット**] をクリックします。

</div>

<div>

## <a name="creating-new-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して新しい Lync Phone Edition 構成設定を作成する

Lync Phone Edition の構成設定は、Windows PowerShell と **get-csucphoneconfiguration** コマンドレットを使用して (サイトスコープでのみ) 作成できます。 このコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-create-new-lync-phone-edition-configuration-settings-that-use-the-default-values"></a>既定値を使用する新しい Lync Phone Edition の構成設定を作成するには

  - 次のコマンドでは、Redmond サイト用に UC 電話構成設定の新しいセットを作成します。
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond"
    
    このコマンドでは (必須の Identity パラメーター以外の) パラメーターが指定されていないため、新しい構成設定のコレクションでは、すべてのプロパティに既定値が使用されます。

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-new-lync-phone-edition-configuration-settings"></a>新しい Lync Phone Edition 構成設定を作成するときに1つのプロパティ値を変更するには

  - 別のプロパティ値を使用する設定を作成するには、該当するパラメーターとパラメータ値を追加します。たとえば、既定で電話のロックを必要とする UC 電話構成設定のコレクションを作成するには、次のようなコマンドを使用します。
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-new-lync-phone-edition-configuration-settings"></a>新しい Lync Phone Edition 構成設定の作成時に複数のプロパティ値を変更するには

  - 複数のパラメーターを含めることにより、複数のプロパティ値を変更できます。たとえば次のコマンドでは、電話のロックを適用し、さらに PIN の最小桁数を 8 桁に設定します。
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True -MinPhonePinLength 8

</div>

詳細については、「 [get-csucphoneconfiguration](https://technet.microsoft.com/library/Gg398445(v=OCS.15))」を参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 の Lync Phone Edition 構成設定の既存コレクションの削除](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[Lync Server 2013 で Lync Phone Edition のセキュリティ設定を構成する](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[Lync Server 2013 での電話ロックの適用](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

