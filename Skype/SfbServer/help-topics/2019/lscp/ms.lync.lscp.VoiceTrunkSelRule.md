---
title: 変換ルールの選択
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceTrunkSelRule
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 55776a94-4888-4436-a3b6-0e6f8252e392
ROBOTS: NOINDEX, NOFOLLOW
description: エンタープライズ VoIP では、すべてのダイヤル文字列が番号の逆引き参照 (RNL) を実行するための E.164 形式に正規化する必要があります。 一方、トランク ピア (つまり、関連付けられたゲートウェイ、PBX、または SIP トランク) では、番号を地域のダイヤル形式にすることが必要な場合もあります。 E.164 形式から地域のダイヤル形式に番号を変換するには、オプションとして、トランク ピアにルーティングする前に 1 つ以上の変換ルールを定義して要求 URI を操作することができます。 たとえば、ダイヤル文字列の先頭から +44 を削除して 0144 に置き換える変換ルールを作成できます。
ms.openlocfilehash: c1a8b5e3506eea97e6f9bab7c455eb31d26f4455
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/24/2018
ms.locfileid: "20998989"
---
# <a name="select-translation-rules"></a>変換ルールの選択
 
 エンタープライズ VoIP では、すべてのダイヤル文字列が番号の逆引き参照 (RNL) を実行するための E.164 形式に正規化する必要があります。 一方、トランク ピア (つまり、関連付けられたゲートウェイ、PBX、または SIP トランク) では、番号を地域のダイヤル形式にすることが必要な場合もあります。 E.164 形式から地域のダイヤル形式に番号を変換するには、オプションとして、トランク ピアにルーティングする前に 1 つ以上の変換ルールを定義して要求 URI を操作することができます。 たとえば、ダイヤル文字列の先頭から +44 を削除して 0144 に置き換える変換ルールを作成できます。
  
> [!IMPORTANT]
> トランク ピアで変換ルールを構成する代わりに使用するものでは 1 つまたは複数の変換ルールをエンタープライズ VoIP のトランク構成に関連付けること。 2 つのルールが競合する可能性がありますので、トランク ピアで変換ルールを構成している場合は、エンタープライズ VoIP のトランク構成の変換規則を関連付けないでください。 
  
既存の変換ルールを使用するには、一覧でルールをクリックして [**OK**] をクリックします。
  
 
  

