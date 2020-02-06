---
title: アナログ デバイスの移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server は、アナログデバイスをサポートしています。 特に、サポートされているアナログデバイスはアナログオーディオ電話とアナログ fax マシンです。 Skype for Business Server 環境でのアナログデバイスの使用をサポートするために、修飾ゲートウェイを構成することができます。 Skype for Business Server 2019 に移行した後は、アナログデバイスに関連付けられた連絡先オブジェクトも移行する必要があります。 Skype for Business Server 管理シェルを使って、従来のアナログデバイスに関連付けられたすべての連絡先オブジェクトを取得してから、それらのオブジェクトを Skype for Business Server 2019 プールに移動します。
ms.openlocfilehash: b3b3cc1ebafa468a43043b202a01957c1cc06e87
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813595"
---
# <a name="migrate-analog-devices"></a>アナログ デバイスの移行

Skype for Business Server は、アナログデバイスをサポートしています。 特に、サポートされているアナログデバイスはアナログオーディオ電話とアナログ fax マシンです。 Skype for Business Server 環境でのアナログデバイスの使用をサポートするために、修飾ゲートウェイを構成することができます。 Skype for Business Server 2019 に移行した後は、アナログデバイスに関連付けられた連絡先オブジェクトも移行する必要があります。 Skype for Business Server 管理シェルを使って、従来のアナログデバイスに関連付けられたすべての連絡先オブジェクトを取得してから、それらのオブジェクトを Skype for Business Server 2019 プールに移動します。

### <a name="to-migrate-analog-devices"></a>アナログデバイスを移行するには

1. Skype for Business Server 管理シェルを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft skype for business Server 2019**]、[ **skype for business server 管理シェル**] の順にクリックします。

2. コマンド ラインで次を入力します。

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. すべての連絡先オブジェクトが Skype for Business Server 2019 プールに移動されていることを確認します。 コマンド ラインで次を入力します。

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. すべての連絡先オブジェクトが Skype for Business Server 2019 プールに関連付けられていることを確認します。


