---
title: アナログ デバイスの移行
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Skype for Business Server は、アナログデバイスのサポートを提供します。 具体的には、アナログ音声電話とアナログ FAX 電話がアナログ デバイスとしてサポートされます。 Skype for Business Server 環境でのアナログデバイスの使用をサポートするために、認定ゲートウェイを構成することができます。 Skype for Business Server 2019 に移行した後で、アナログデバイスに関連付けられている連絡先オブジェクトも移行する必要があります。 Skype for Business Server 管理シェルを使用して、従来のアナログデバイスに関連付けられているすべての連絡先オブジェクトを最初に取得し、そのオブジェクトを Skype for Business Server 2019 プールに移動します。
ms.openlocfilehash: 7b90a52486725c2cf30856dc643660d569d698e2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752829"
---
# <a name="migrate-analog-devices"></a>アナログ デバイスの移行

Skype for Business Server は、アナログデバイスのサポートを提供します。 具体的には、アナログ音声電話とアナログ FAX 電話がアナログ デバイスとしてサポートされます。 Skype for Business Server 環境でのアナログデバイスの使用をサポートするために、認定ゲートウェイを構成することができます。 Skype for Business Server 2019 に移行した後で、アナログデバイスに関連付けられている連絡先オブジェクトも移行する必要があります。 Skype for Business Server 管理シェルを使用して、従来のアナログデバイスに関連付けられているすべての連絡先オブジェクトを最初に取得し、そのオブジェクトを Skype for Business Server 2019 プールに移動します。

### <a name="to-migrate-analog-devices"></a>アナログ デバイスを移行するには

1. Skype for Business Server 管理シェルを起動します。 [**スタート**]、[**すべてのプログラム**]、[ **Microsoft Skype for business Server 2019**]、[ **skype for business server 管理シェル**] の順にクリックします。

2. コマンドラインで、次のように入力します。

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsAnalogDevice -Target pool02.contoso.net
   ```

3. すべての連絡先オブジェクトが Skype for Business Server 2019 プールに移動されたことを確認します。 コマンドラインで、次のように入力します。

   ```PowerShell
   Get-CsAnalogDevice -Filter {RegistrarPool -eq "pool02.contoso.net"}
   ```

4. すべての連絡先オブジェクトが Skype for Business Server 2019 プールに関連付けられていることを確認します。


