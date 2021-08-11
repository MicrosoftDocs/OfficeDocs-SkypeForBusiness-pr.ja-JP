---
title: インフラストラクチャのコア インフラストラクチャのベスト プラクティスSkype for Business Server
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
description: 一般に、システムのフォールト トレランスを構築する方法として、ハードウェアを冗長構成にする、給電が途切れないようにする、セキュリティ更新プログラムやウイルス対策を定期的にインストールする、サーバーの利用状況を監視するなどの手段を既に講じていることでしょう。 これらのプラクティスは、インフラストラクチャだけでなくSkype for Business Serverネットワーク全体にもメリットがあります。 これらのプラクティスを実装していない場合は、展開する前に実行することをお勧Skype for Business Server。
ms.openlocfilehash: 21173b6fe924938ebabfecc0c36b3abdce092b4c9e902284530ec47d2c1ca8bf
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/05/2021
ms.locfileid: "54318702"
---
# <a name="best-practices-for-your-core-infrastructure-in-skype-for-business-server"></a>インフラストラクチャのコア インフラストラクチャのベスト プラクティスSkype for Business Server
 
一般に、システムのフォールト トレランスを構築する方法として、ハードウェアを冗長構成にする、給電が途切れないようにする、セキュリティ更新プログラムやウイルス対策を定期的にインストールする、サーバーの利用状況を監視するなどの手段を既に講じていることでしょう。 これらのプラクティスは、インフラストラクチャだけでなくSkype for Business Serverネットワーク全体にもメリットがあります。 これらのプラクティスを実装していない場合は、展開する前に実行することをお勧Skype for Business Server。
  
ダウンタイムの原因になる可能性のある偶発的Skype for Business Server、または目的に合った危害からサーバーを保護するために、次の予防措置を講じられます。
  
- 各サーバーに、常に最新のセキュリティ更新プログラムを適用します。 マイクロソフト テクニカル セキュリティ情報通知サービスに登録すると、マイクロソフト製品に関するセキュリティ速報を受信できます。 購読するには、Microsoft Technical Security Notifications Web サイト [にアクセスします](https://go.microsoft.com/fwlink/p/?LinkId=145202)。
    
- アクセス権が正しく設定されていることを確認します。
    
- 物理環境のサーバーが不正アクセスされないようにします。すべてのサーバーに適切なウイルス対策ソフトウェアをインストールします。最新のウイルス シグネチャ ファイルを適用して、ウイルス対策ソフトウェアを常に最新状態に保ちます。ウイルス対策ソフトウェアの自動更新機能を使用して、ウイルス シグネチャ ファイルを常に最新状態に保ちます。
    
- サーバーをインストールするコンピューター Windowsサーバー オペレーティング システム サービスを無効にすることをおSkype for Business Server。
    
- サーバーの一貫した完全な制御、全体での物理的な分離、および交換するディスク ドライブまたは故障したディスク ドライブの適切かつ安全な使用停止を保証できない場合は、オペレーティング システムとデータが格納されるディスク ドライブをフルボリューム暗号化システムで暗号化します。
    
- サーバーへの物理アクセスを厳密に制御できない場合は、サーバーの外部直接メモリ アクセス (DMA) ポートをすべて無効にします。 DMA を利用した攻撃は非常に簡単で、秘密暗号化キーなど、きわめて機密性の高い情報が盗まれる可能性があります。
    

