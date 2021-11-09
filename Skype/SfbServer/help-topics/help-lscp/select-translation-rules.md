---
title: 変換ルールの選択
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.VoiceTrunkSelRule
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 55776a94-4888-4436-a3b6-0e6f8252e392
description: エンタープライズ VoIP、逆引き番号参照 (RNL) を実行するために、すべてのダイヤル文字列を E.164 形式に正規化する必要があります。 一方、トランク ピア (つまり、関連付けられたゲートウェイ、PBX、または SIP トランク) では、番号を地域のダイヤル形式にすることが必要な場合もあります。 E.164 形式から地域のダイヤル形式に番号を変換するには、オプションとして、トランク ピアにルーティングする前に 1 つ以上の変換ルールを定義して Request URI を操作することができます。 たとえば、ダイヤル文字列の先頭から +44 を削除して 0144 に置き換える変換ルールを作成できます。
ms.openlocfilehash: 5776f97b5d5f34ce85696d7ae0c227fdfe8cf263
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/08/2021
ms.locfileid: "60862724"
---
# <a name="select-translation-rules"></a>変換ルールの選択
 
 エンタープライズ VoIP、逆引き番号参照 (RNL) を実行するために、すべてのダイヤル文字列を E.164 形式に正規化する必要があります。 一方、トランク ピア (つまり、関連付けられたゲートウェイ、PBX、または SIP トランク) では、番号を地域のダイヤル形式にすることが必要な場合もあります。 E.164 形式から地域のダイヤル形式に番号を変換するには、オプションとして、トランク ピアにルーティングする前に 1 つ以上の変換ルールを定義して Request URI を操作することができます。 たとえば、ダイヤル文字列の先頭から +44 を削除して 0144 に置き換える変換ルールを作成できます。
  
> [!IMPORTANT]
> 1 つ以上の変換ルールをエンタープライズ VoIP のトランク構成と関連付ける機能は、トランク ピアに変換ルールを構成することの代替として使用されます。 トランク ピアで変換ルールを構成した場合は、2 つのルールが競合する可能性があるため、変換ルールをエンタープライズ VoIP トランク構成に関連付けないでください。 
  
既存の変換ルールを使用するには、一覧でルールをクリックして [**OK**] をクリックします。
  
コントロール パネルを使用して実行できるさまざまな手順の詳細については、「Skype for Business Server [2015」](../../manage/manage.md)を参照Skype for Business Serverしてください。
  

