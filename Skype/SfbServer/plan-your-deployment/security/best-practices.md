---
title: Skype for Business Server のコアインフラストラクチャのベストプラクティス
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
description: システムのフォールト トレランスを構築する方法として、ハードウェアを冗長構成にする、給電が途切れないようにする、セキュリティ更新プログラムやウイルス対策を定期的にインストールする、サーバーの利用状況を監視するなどの手段をすでに講じていることでしょう。 この方法は、Skype for Business Server インフラストラクチャだけでなく、ネットワーク全体でもメリットがあります。 これらのプラクティスを実装していない場合は、Skype for Business Server を展開する前に、この手順を実行することをお勧めします。
ms.openlocfilehash: 62200fc1ac45e1d647761af24d176a00d18693e4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815685"
---
# <a name="best-practices-for-your-core-infrastructure-in-skype-for-business-server"></a>Skype for Business Server のコアインフラストラクチャのベストプラクティス
 
システムのフォールト トレランスを構築する方法として、ハードウェアを冗長構成にする、給電が途切れないようにする、セキュリティ更新プログラムやウイルス対策を定期的にインストールする、サーバーの利用状況を監視するなどの手段をすでに講じていることでしょう。 この方法は、Skype for Business Server インフラストラクチャだけでなく、ネットワーク全体でもメリットがあります。 これらのプラクティスを実装していない場合は、Skype for Business Server を展開する前に、この手順を実行することをお勧めします。
  
ダウンタイムが発生する可能性のある偶発的または明確の危害から Skype for Business Server 展開のサーバーを保護するには、次のことを行う必要があります。
  
- 各サーバーに、常に最新のセキュリティ更新プログラムを適用します。 マイクロソフト テクニカル セキュリティ情報通知を購読すると、マイクロソフト製品に関するセキュリティ速報を受信できます。 登録するには、 [Microsoft テクニカルセキュリティ通知の web サイト](https://go.microsoft.com/fwlink/p/?LinkId=145202)にアクセスしてください。
    
- アクセス権が正しく設定されていることを確認します。
    
- 物理環境のサーバーが不正アクセスされないようにします。すべてのサーバーに適切なウイルス対策ソフトウェアをインストールします。最新のウイルス シグネチャ ファイルを適用して、ウイルス対策ソフトウェアを常に最新状態に保ちます。ウイルス対策ソフトウェアの自動更新機能を使用して、ウイルス シグネチャ ファイルを常に最新状態に保ちます。
    
- Skype for Business Server をインストールするコンピューターには必要ない Windows Server オペレーティングシステムサービスを無効にすることをお勧めします。
    
- サーバーの一貫した完全な制御、全体での物理的な分離、および交換するディスク ドライブまたは故障したディスク ドライブの適切かつ安全な使用停止を保証できない場合は、オペレーティング システムとデータが格納されるディスク ドライブをフルボリューム暗号化システムで暗号化します。
    
- サーバーへの物理アクセスを厳密に制御できない場合は、サーバーの外部直接メモリ アクセス (DMA) ポートをすべて無効にします。 DMA を利用した攻撃は非常に簡単で、秘密暗号化キーなど、きわめて機密性の高い情報が盗まれる可能性があります。
    

