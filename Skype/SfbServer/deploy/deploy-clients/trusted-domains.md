---
title: Skype Room System の信頼されたドメイン
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: このトピックでは、Skype Room System と Skype for Business の信頼されたドメインを構成する方法について説明します。
ms.openlocfilehash: c7883ed0cbc2e805ee0ba3cddfb3b2cee1163c35
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834117"
---
# <a name="skype-room-system-trusted-domains"></a>Skype Room System の信頼されたドメイン
 
このトピックでは、Skype Room System と Skype for Business の信頼されたドメインを構成する方法について説明します。
  
## <a name="trusted-domains"></a>信頼済みドメイン

サインインするユーザー アカウントの SIP ドメインが、証明書のサブジェクト名またはサブジェクトの代替名に表示される名前と異なる場合、Skype for Business クライアントは Skype for Business Server からの証明書を受け入れ可能なダイアログ ボックスを表示します。 組織内の Skype for Business Server 用に構成された証明書に、サブジェクト名またはサブジェクト代替名に Skype Room System アカウントの SIP ドメイン名が設定されていない場合は、Skype Room System コンソール コンピューターの信頼されたドメイン レジストリ キーの下にある証明書に表示されるドメインを構成する必要があります。 Skype Room System の製造元が提供する Skype Room System Administrator's Guide では、Skype for Business クライアントで信頼されたドメインを追加する方法と場所について説明します。 
  
たとえば、Skype for Business Server で構成された証明書のサブジェクト/サブジェクトの代替名が "CONTOSO" だとします。LOCAL" と Skype Room System サインイン アドレスのユーザーに割り当てられている SIP ドメインの 1 つが "confrm1@contoso.net" です。 contoso.net は証明書に含めないので、Skype Room System の製造元が提供する Skype Room System 管理者ガイドで説明したように、レジストリで "contoso.local" を信頼されたドメインとして構成する必要があります。 
  

