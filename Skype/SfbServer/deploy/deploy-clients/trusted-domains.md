---
title: Skype Room System の信頼されたドメイン
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9fb63ad4-6eda-4724-be63-10bf5e65cb2b
description: このトピックでは、Skype Room System および Skype for Business で信頼されたドメインを構成する方法について説明します。
ms.openlocfilehash: ff8f75178fef21900292760fb71f53ea3746380c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/11/2019
ms.locfileid: "33895048"
---
# <a name="skype-room-system-trusted-domains"></a>Skype Room System の信頼されたドメイン
 
このトピックでは、Skype Room System および Skype for Business で信頼されたドメインを構成する方法について説明します。
  
## <a name="trusted-domains"></a>信頼されたドメイン

ビジネス クライアント用の Skype では、ビジネスのサーバーのサインイン時にユーザー アカウントの SIP ドメインの証明書のサブジェクトまたはサブジェクトの alt キーを押し名の表示名と異なる場合、Skype からの証明書を受け入れるようにユーザーを許可する] ダイアログ ボックスが表示されます。 それらのドメインが信頼されたドメイン] で [証明書の提示を構成する必要がある場合は、組織のビジネス サーバーの Skype 用に構成された証明書には、件名または件名の alt キーを押し、Skype ルームのシステム アカウントの SIP ドメインの名前がありません、Skype ルーム システム コンソール コンピューター上のレジストリ キーです。 Skype ルーム システムの製造元から提供された Skype ルーム システム管理者ガイド 』 の説明方法と場所、Skype ビジネス クライアント用の信頼されたドメインを追加します。 
  
たとえば、Skype ビジネス サーバーの構成、証明書は、"CONTOSO の件名または件名の alt キーを押し名前を付けます。ローカル"と Skype ルーム システムのサインイン用アドレスのユーザーに割り当てられている SIP ドメインの 1 つは、「confrm1@contoso.net です」 Skype ルーム システム コンピューター上の証明書ではなく contoso.net であるため、Skype ルーム システムの製造元から提供された Skype ルーム システム管理者ガイド 』 で説明したように、レジストリ内の信頼されたドメインとして"contoso.local"を構成する必要があります。 
  

