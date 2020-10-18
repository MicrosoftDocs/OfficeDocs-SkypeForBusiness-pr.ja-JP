---
title: デバイス更新の構成設定のコレクションの作成または変更
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of Device Update configuration settings
ms:assetid: 3e8ce95f-a8c8-417c-b1f7-0f759a567aff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994029(v=OCS.15)
ms:contentKeyID: 51803938
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f5ec896951f96c1e5059968ea0998742a90957c0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525854"
---
# <a name="create-or-modify-a-collection-of-device-update-configuration-settings-in-lync-server-2013"></a>Lync Server 2013 でのデバイス更新の構成設定のコレクションの作成または変更

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**トピックの最終更新日:** 2013-02-23_

デバイス更新の構成設定は Windows PowerShell および **New-CsDeviceUpdateConfiguration** コマンドレットを使用して (サイト スコープでのみ) 作成でき、**Set-CsDeviceUpdateConfiguration** コマンドレットを使用して変更できます。 これらのコマンドレットは、Lync Server 2013 管理シェルまたは Windows PowerShell のリモート セッションから実行できます。

<div>


> [!NOTE]
> リモートの Windows PowerShell を使用して Lync Server に接続する方法について詳しくは、Lync Server Windows PowerShell のブログ記事「Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell (クイックスタート: リモート PowerShell を使用した Microsoft Lync Server 2010 の管理)」を<A href="https://go.microsoft.com/fwlink/p/?linkid=255876">https://go.microsoft.com/fwlink/p/?linkId=255876</A>で参照してください。



</div>

<div>


<div>

## <a name="to-create-device-update-configuration-settings-that-use-the-default-values"></a>既定値を使用するデバイス更新の構成設定を作成するには

  - このコマンドは、Redmond サイト用にデバイス更新の構成設定の新しいセットを作成します。
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond"
    
    前述のコマンドでは、必須の Identity パラメーター以外のパラメーターは指定されていないので、新しい構成設定のコレクションではすべてのプロパティで既定値が使用されます。

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-device-update-configuration-settings"></a>デバイス更新の構成設定の作成時に 1 つのプロパティ値を変更するには

  - 異なるプロパティ値を使用する設定を作成するには、適切なパラメーターとパラメーター値を含めるだけです。 たとえば、規定で古いログファイルを 21 日ごとに削除するデバイス更新の構成設定のコレクションを作成するには、次のようなコマンドを使用します。
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00"

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-device-update-configuration-settings"></a>デバイス更新の構成設定の作成時に複数のプロパティ値を変更するには

  - 複数のプロパティ値は、複数のパラメーターを含めることによって変更できます。 たとえば、次のコマンドでは、ログのクリーンアップ間隔を 21 日に設定し、さらにログのフラッシュ間隔を 30 分に設定します。
    
        New-CsDeviceUpdateConfiguration -Identity "site:Redmond" -LogCleanupInterval "21.00:00:00" -LogFlushInterval "00:30:00"

</div>

既存のデバイス構成設定の変更の詳細については、[Set-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg398320(v=OCS.15)) コマンドレットのヘルプ トピックを参照してください。 構成設定コレクションの作成の詳細については、 [New-CsDeviceUpdateConfiguration](https://technet.microsoft.com/library/Gg425761(v=OCS.15)) コマンドレットのヘルプ トピックを参照してください。

</div>

</div>

<span> </span>

</div>

</div>

</div>

