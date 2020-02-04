---
title: Lync Phone Edition の構成設定のコレクションを作成または変更する
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
ms.openlocfilehash: 6b3eaf347693d079ef713716c5ebd0d8c470feef
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763349"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a>Lync Server 2013 で Lync Phone エディションの構成設定のコレクションを作成または変更する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

Lync Server をインストールすると、Lync Phone Edition の設定のグローバルコレクションが取得されます。 これらの設定は、展開で Lync Phone Edition を実行しているすべてのデバイスに適用されます。 これらの設定はいつでも変更できます。 また、特定のサイトのデバイスに適用される新しい設定のコレクションを設定することもできます。 サイトの設定はグローバル設定よりも優先されます。

構成設定は、コレクション名、スコープ (グローバルまたはサイト)、SIP セキュリティ設定、ログレベル、音声品質サービス (QoS) レベル、電話ロック設定、および電話ロックの詳細 (a) による個人識別番号のロック解除 (時間) で構成されています (PIN) と b) 電話をロックする前に、アイドル状態のままにしておく必要があります。

<div>

## <a name="to-create-a-collection-of-lync-phone-edition-configuration-settings-or-edit-settings-for-an-existing-collection"></a>Lync Phone Edition の構成設定のコレクションを作成する、または既存のコレクションの設定を編集するには

1.  CsUserAdministrator または CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  ブラウザーウィンドウを開き、管理 URL を入力して Lync Server コントロールパネルを開きます。 Lync Server コントロールパネルを起動するために使用できるさまざまな方法について詳しくは、「 [Lync server 2013 管理ツールを開く](lync-server-2013-open-lync-server-administrative-tools.md)」をご覧ください。

3.  左側のナビゲーションバーで、[**クライアント**] をクリックし、[**デバイス構成**] ナビゲーションボタンをクリックします。

4.  [**デバイスの構成**] ページで、次のいずれかの操作を行います。
    
      - 新しいコレクションを作成するには、[**新規**作成] をクリックし、サイトを選択して、[ **OK**] をクリックし、既定の設定を確認し、必要に応じて変更を加えます。
    
      - 既存のコレクションのいずれかの設定を編集するには、コレクションをクリックし、[**編集**] メニューの [**詳細の表示**] をクリックして、変更を加えます。
        
        <div>
        

        > [!TIP]
        > グローバルコレクションの既定の設定を使用して元に戻すには、グローバルコレクションをクリックし、[<STRONG>編集</STRONG>] メニューの [<STRONG>削除</STRONG>] をクリックして、[ <STRONG>OK]</STRONG>をクリックします。 グローバルコレクションが削除されることはありません。単に設定を既定値にリセットします。

        
        </div>

5.  [**コミット**] をクリックします。

</div>

<div>

## <a name="creating-new-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a>Windows PowerShell コマンドレットを使用して新しい Lync Phone エディション構成設定を作成する

Lync Phone Edition の構成設定は、Windows PowerShell と**CsUCPhoneConfiguration**コマンドレットを使用して (サイトのスコープでのみ) 作成できます。 このコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。 リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を[http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)で参照してください。

<div>

## <a name="to-create-new-lync-phone-edition-configuration-settings-that-use-the-default-values"></a>既定値を使用する新しい Lync Phone Edition の構成設定を作成するには

  - このコマンドを実行すると、Redmond サイト用に UC 電話構成の新しい設定が作成されます。
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond"
    
    前述のコマンドでは、必須の Identity パラメーター以外のパラメーターは指定されていないため、新しい構成設定のコレクションではすべてのプロパティで既定値が使用されます。

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-new-lync-phone-edition-configuration-settings"></a>新しい Lync Phone エディション構成設定の作成時に1つのプロパティ値を変更するには

  - 異なるプロパティ値を使用する設定を作成するには、適切なパラメーターとパラメーター値を含めるだけです。 たとえば、既定で電話のロックを要求する UC 電話構成設定のコレクションを作成するには、次のようなコマンドを使用します。
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-new-lync-phone-edition-configuration-settings"></a>新しい Lync Phone エディションの構成設定を作成するときに、複数のプロパティの値を変更するには

  - 複数のプロパティ値は、複数のパラメーターを含めることによって変更できます。 たとえば、次のコマンドでは、電話のロックが強制され、PIN の最小の長さが8桁に設定されます。
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True -MinPhonePinLength 8

</div>

詳細については、「 [New-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398445(v=OCS.15))」を参照してください。

</div>

<div>

## <a name="see-also"></a>関連項目


[Lync Server 2013 で既存の Lync Phone エディション構成の設定を削除する](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[Lync Server 2013 で Lync Phone Edition のセキュリティ設定を構成する](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[Lync Server 2013 での電話のロックを適用する](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

