---
title: 変換ルールの選択
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.VoiceTrunkSelRule
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 55776a94-4888-4436-a3b6-0e6f8252e392
ROBOTS: NOINDEX, NOFOLLOW
description: エンタープライズボイスでは、逆引き数値参照 (RNL) を実行するために、すべてのダイヤル文字列が E.i 形式に正規化されている必要があります。 一方、トランク ピア (つまり、関連付けられたゲートウェイ、PBX、または SIP トランク) では、番号を地域のダイヤル形式にすることが必要な場合もあります。 E.164 形式から地域のダイヤル形式に番号を変換するには、オプションとして、トランク ピアにルーティングする前に 1 つ以上の変換ルールを定義して要求 URI を操作することができます。 たとえば、ダイヤル文字列の先頭から +44 を削除して 0144 に置き換える変換ルールを作成できます。
ms.openlocfilehash: e6df4b2eed01849af7290596bc0e91896e527574
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/20/2019
ms.locfileid: "34290718"
---
# <a name="select-translation-rules"></a>変換ルールの選択
 
 エンタープライズボイスでは、逆引き数値参照 (RNL) を実行するために、すべてのダイヤル文字列が E.i 形式に正規化されている必要があります。 一方、トランク ピア (つまり、関連付けられたゲートウェイ、PBX、または SIP トランク) では、番号を地域のダイヤル形式にすることが必要な場合もあります。 E.164 形式から地域のダイヤル形式に番号を変換するには、オプションとして、トランク ピアにルーティングする前に 1 つ以上の変換ルールを定義して要求 URI を操作することができます。 たとえば、ダイヤル文字列の先頭から +44 を削除して 0144 に置き換える変換ルールを作成できます。
  
> [!IMPORTANT]
> エンタープライズボイストランク構成に1つまたは複数の翻訳ルールを関連付ける機能は、トランクピアでの翻訳ルールの設定の代わりとして使用することを目的としています。 2つのルールが競合する可能性があるため、トランクピアで翻訳ルールを構成している場合、翻訳ルールをエンタープライズボイストランク構成に関連付けないでください。 
  
既存の変換ルールを使用するには、一覧でルールをクリックして [**OK**] をクリックします。
  
 
  

