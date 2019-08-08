---
title: 省略Skype for Business のコールパークの展開を確認する
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
description: Skype for Business Server Enterprise Voice でのコールパークの展開を確認します。
ms.openlocfilehash: d698bf46f0a36a86729856c388fde09514288253
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240438"
---
# <a name="optional-verify-call-park-deployment-in-skype-for-business"></a>省略Skype for Business のコールパークの展開を確認する
 
Skype for Business Server Enterprise Voice でのコールパークの展開を確認します。 
  
コールパークのインストールと構成が完了したら、構成を確認して、パーキングと着信の取得が期待どおりに動作することを確認する必要があります。 少なくとも、以下を確認してください。
  
- コールパークが有効になっていて、ユーザが通話をパークしているユーザに電話をかけます。
    
    > [!NOTE]
    > このテストを実行する前に、音声ポリシーでコールパークを有効にしている場合は、その通話を保留にしているユーザーが Skype for Business からサインアウトしてから、もう一度サインインすると、[着信の転送] リストの [通話パーク] オプションが表示されます。 
  
- オービット番号をダイヤルして、電話を取ります。
    
- 別の通話を保留して、保留した通話がタイムアウトするようにして、リングバックは取らないようにします。タイムアウトした通話が **OnTimeoutURI** で指定されているフォールバック宛先に正しくルーティングされていることを確認します。
    

