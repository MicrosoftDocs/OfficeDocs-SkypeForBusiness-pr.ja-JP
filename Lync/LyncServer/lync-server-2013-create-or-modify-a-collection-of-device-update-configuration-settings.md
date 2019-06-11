---
title: デバイス更新構成設定のコレクションを作成または変更する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a collection of Device Update configuration settings
ms:assetid: 3e8ce95f-a8c8-417c-b1f7-0f759a567aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994029(v=OCS.15)
ms:contentKeyID: 51803938
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d5b53ff6e876a2c5226b6728e0ebde95d55e7ea
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "34833801"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-device-update-configuration-settings-in-lync-server-2013"></a>Lync Server 2013 でデバイス更新プログラムの構成設定のコレクションを作成または変更する

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**最終更新日:** 2013-02-23_

デバイスの更新の構成設定は (サイトのスコープでのみ) 作成できます。 Windows PowerShell と**新しい-csdeviceupdateconfiguration**コマンドレットを使用して、 **Set-csdeviceupdateconfiguration**コマンドレットを使用して変更します。 これらのコマンドレットは、Lync Server 2013 管理シェルから、または Windows PowerShell のリモートセッションから実行できます。

<div>


> [!NOTE]
> リモートの Windows PowerShell を使用して Lync Server に接続する方法の詳細については、「Lync Server Windows PowerShell のブログ記事」を参照してください<A href="http://go.microsoft.com/fwlink/p/?linkid=255876">http://go.microsoft.com/fwlink/p/?linkId=255876</A>。「リモート PowerShell を使用して Microsoft Lync Server 2010 を管理する」を参照してください。



</div>

<div>


<div>

## <a name="to-create-device-update-configuration-settings-that-use-the-default-values"></a>既定値を使用するデバイス更新設定を作成するには

  - このコマンドによって、Redmond サイト用の新しいデバイス更新構成の設定が作成されます。
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond"
    
    必須の Identity パラメーター以外のパラメーターは前のコマンドで指定されているため、構成設定の新しいコレクションでは、すべてのプロパティに既定値が使用されます。

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-device-update-configuration-settings"></a>デバイス更新構成設定の作成時に1つのプロパティ値を変更するには

  - 異なるプロパティ値を使用する設定を作成するには、適切なパラメーターとパラメーター値を指定します。 たとえば、最初に21日間ごとに古いログファイルを削除するデバイスの更新構成設定のコレクションを作成するには、次のようなコマンドを使用します。
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-device-update-configuration-settings"></a>デバイス更新構成設定の作成時に複数のプロパティ値を変更するには

  - 複数のパラメーターを含めることにより複数のプロパティ値を変更できます。 たとえば、次のコマンドは、ログのクリーンアップ間隔を21日に設定し、ログのフラッシュ間隔を30分に設定します。
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00" -LogFlushInterval "00:30:00"

</div>

既存のデバイス構成設定の変更の詳細については、「 [Set-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg398320(v=OCS.15))コマンドレット」のヘルプトピックを参照してください。 構成設定のコレクションの作成の詳細については、「[新しい-CsDeviceUpdateConfiguration](https://technet.microsoft.com/en-us/library/Gg425761(v=OCS.15))コマンドレット」のヘルプトピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

