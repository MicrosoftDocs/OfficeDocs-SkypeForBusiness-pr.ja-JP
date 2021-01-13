---
title: Skype for Business Server のコア インフラストラクチャのベスト プラクティス
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 44aff88d-536c-4613-a81e-5398c9c6a648
description: 一般に、システムのフォールト トレランスを構築する方法として、ハードウェアを冗長構成にする、給電が途切れないようにする、セキュリティ更新プログラムやウイルス対策を定期的にインストールする、サーバーの利用状況を監視するなどの手段を既に講じていることでしょう。 これらのプラクティスは、Skype for Business Server インフラストラクチャだけでなく、ネットワーク全体にもメリットがあります。 これらのプラクティスを実装していない場合は、Skype for Business Server を展開する前に実装することをお勧めします。
ms.openlocfilehash: f2e9e019c5aadab57dddc8d8dcbb1b9090a160f4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832247"
---
# <a name="best-practices-for-your-core-infrastructure-in-skype-for-business-server"></a>Skype for Business Server のコア インフラストラクチャのベスト プラクティス
 
一般に、システムのフォールト トレランスを構築する方法として、ハードウェアを冗長構成にする、給電が途切れないようにする、セキュリティ更新プログラムやウイルス対策を定期的にインストールする、サーバーの利用状況を監視するなどの手段を既に講じていることでしょう。 これらのプラクティスは、Skype for Business Server インフラストラクチャだけでなく、ネットワーク全体にもメリットがあります。 これらのプラクティスを実装していない場合は、Skype for Business Server を展開する前に実装することをお勧めします。
  
Skype for Business Server 展開内のサーバーを、ダウンタイムの原因になる偶発的または目的上の損害から保護するには、次の予防措置を講じます。
  
- 各サーバーに、常に最新のセキュリティ更新プログラムを適用します。 マイクロソフト テクニカル セキュリティ情報通知サービスに登録すると、マイクロソフト製品に関するセキュリティ速報を受信できます。 To subscribe, go to the [Microsoft Technical Security Notifications website](https://go.microsoft.com/fwlink/p/?LinkId=145202).
    
- アクセス権が正しく設定されていることを確認します。
    
- 物理環境のサーバーが不正アクセスされないようにします。すべてのサーバーに適切なウイルス対策ソフトウェアをインストールします。最新のウイルス シグネチャ ファイルを適用して、ウイルス対策ソフトウェアを常に最新状態に保ちます。ウイルス対策ソフトウェアの自動更新機能を使用して、ウイルス シグネチャ ファイルを常に最新状態に保ちます。
    
- Skype for Business Server をインストールするコンピューターで不要な Windows Server オペレーティング システム サービスを無効にすることをお勧めします。
    
- サーバーの一貫した完全な制御、全体での物理的な分離、および交換するディスク ドライブまたは故障したディスク ドライブの適切かつ安全な使用停止を保証できない場合は、オペレーティング システムとデータが格納されるディスク ドライブをフルボリューム暗号化システムで暗号化します。
    
- サーバーへの物理アクセスを厳密に制御できない場合は、サーバーの外部直接メモリ アクセス (DMA) ポートをすべて無効にします。 DMA を利用した攻撃は非常に簡単で、秘密暗号化キーなど、きわめて機密性の高い情報が盗まれる可能性があります。
    

