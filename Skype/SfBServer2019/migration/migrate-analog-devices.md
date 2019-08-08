---
title: アナログ デバイスの移行
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Skype for Business Server は、アナログデバイスをサポートしています。 特に、サポートされているアナログデバイスはアナログオーディオ電話とアナログ fax マシンです。 Skype for Business Server 環境でのアナログデバイスの使用をサポートするために、修飾ゲートウェイを構成することができます。 Skype for Business Server 2019 に移行した後は、アナログデバイスに関連付けられた連絡先オブジェクトも移行する必要があります。 Skype for Business Server 管理シェルを使って、従来のアナログデバイスに関連付けられたすべての連絡先オブジェクトを取得してから、それらのオブジェクトを Skype for Business Server 2019 プールに移動します。
ms.openlocfilehash: 486c49c0ace00b798520ebae939c0c2070a99783
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36238040"
---
# <a name="migrate-analog-devices"></a>アナログ デバイスの移行

Skype for Business Server は、アナログデバイスをサポートしています。 特に、サポートされているアナログデバイスはアナログオーディオ電話とアナログ fax マシンです。 Skype for Business Server 環境でのアナログデバイスの使用をサポートするために、修飾ゲートウェイを構成することができます。 Skype for Business Server 2019 に移行した後は、アナログデバイスに関連付けられた連絡先オブジェクトも移行する必要があります。 Skype for Business Server 管理シェルを使って、従来のアナログデバイスに関連付けられたすべての連絡先オブジェクトを取得してから、それらのオブジェクトを Skype for Business Server 2019 プールに移動します。

### <a name="to-migrate-analog-devices"></a>アナログデバイスを移行するには

1. Skype for Business Server 管理シェルを開始します。 [**スタート**] をクリックし、[**すべてのプログラム**]、[ **Microsoft skype for business Server 2019**]、[ **skype for business server 管理シェル**] の順にクリックします。

2. コマンド ラインで次を入力します。

   ```
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. すべての連絡先オブジェクトが Skype for Business Server 2019 プールに移動されていることを確認します。 コマンド ラインで次を入力します。

   ```
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. すべての連絡先オブジェクトが Skype for Business Server 2019 プールに関連付けられていることを確認します。


