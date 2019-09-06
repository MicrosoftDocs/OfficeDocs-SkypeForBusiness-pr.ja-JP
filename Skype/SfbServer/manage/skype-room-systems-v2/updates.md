---
title: Microsoft Teams ルームの Windows 更新プログラムを管理する
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
ms.date: 10/10/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: M365-voice
ms.assetid: ''
description: Microsoft Teams ルームの Windows 更新プログラムを管理する
ms.openlocfilehash: 09be03b0308dfcf00a39421e2e84b75fe94a9fae
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/06/2019
ms.locfileid: "36775318"
---
# <a name="manage-windows-updates"></a>Windows の更新プログラムを管理する

Microsoft Teams の会議は、Windows 10 Enterprise IoT または Windows 10 Enterprise (VL) で実行され、標準デスクトップと同じ Windows 更新プログラムと OS ビルドを受け取ります。

Windows 更新プログラムを管理するには、次のような方法があります。

## <a name="hands-off-approach"></a>ハンドオフアプローチ 
- 更新プログラムは、Windows 更新プログラムから直接ダウンロードして、業務時間外にインストールすることができます。 構成に変更が行われていない場合は、これが既定の状態になります。
- 遅延不可の更新プログラムでは、リリースの1日目が自動的にインストールされます。 
- 品質更新プログラムとドライバーは、1日の予定を自動的にダウンロードしてインストールします。 
- 機能の更新。 以下の追加のメモを参照してください。 

## <a name="windows-updates-for-businesshttpsdocsmicrosoftcomwindowsdeploymentupdatewaas-manage-updates-wufb-gpo-or-intune"></a>一般[法人向け Windows 更新プログラム](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-wufb)(GPO または Intune)   
- 更新プログラムは WU または WSUS からダウンロードされますが、KB の最初のリリース日よりも遅延が構成されています。 
- 複数の OU またはフィルター処理されたポリシーと組み合わせることで、管理者が品質更新プログラムをインストールするデバイスを指定し、後でインストールするデバイスを指定できる展開用の "呼び出し" を作成できます。 これにより、システムのサブセットに対する信頼性とパフォーマンスのテストを行うことができます。これにより、SCCM での Windows の更新プログラムの管理に伴うオーバーヘッドを生じることなく、展開全体で更新プログラムをロールアウトすることができます。
- 帯域幅の管理と、ビジネス向けの Windows Update の制御の両方が必要な場合は、WSUS と Windows の更新プログラムを同時[に構成](https://docs.microsoft.com/windows/deployment/update/waas-integrate-wufb)することができます。
- 機能の更新。 以下の追加のメモを参照してください。

## <a name="wsussccmhttpsdocsmicrosoftcomwindowsdeploymentupdatewaas-manage-updates-configuration-manager"></a>[WSUS/SCCM](https://docs.microsoft.com/windows/deployment/update/waas-manage-updates-configuration-manager)
- 一般法人向け Windows Update と同じように、各 "リング" または展開全体で特定の KB をターゲットに設定するための追加オプションがあります。 各更新プログラムは、遅延のみではなく、個別に展開してテストすることができます。 
- 機能の更新。 以下の追加のメモを参照してください。


### <a name="feature-updates"></a>機能の更新プログラム

品質と Deferable 以外の更新プログラムとは異なり、Windows 10 "機能更新プログラム" (メジャー OS リリース) は、Microsoft テストの後にのみインストールされ、Microsoft Teams のルームで特定の更新機能を検証します。 半期チャネルにリリースされた場合 (またはテスト用にそのチャネルにシステムを設定している場合)、または独自の試みや構成で手動でプッシュした場合でも、そのエンドのブロックが削除されるまで、インストールは許可されません。

ハンズオフアプローチを使用した Microsoft Teams Room "box" は、Windows update をインストールしたり、windows update のためにデバイスを自動的に再起動したりすることはありません。 ただし、システムによって更新プログラムがダウンロードされ、次に再起動するまで待ってからインストールできる場合があります。 手動で再起動しない限り、自動夜間再起動時にインストールが行われます。 Windows の更新プログラムは、会議室では透過的である必要があります。 UI は Windows 更新プログラムによって中断されることはありません。

ドメイン参加を選択する場合は、SCCM または WSUS を使用し、デバイスで更新プログラムをインストールしたり、業務時間中に再起動を強制したりする可能性のあるポリシーまたは操作に特に注意してください。 展開されているシステムが、使用中に、または UI を介した Windows 更新に関する通知中に再起動する場合は、構成を確認する必要があります。
