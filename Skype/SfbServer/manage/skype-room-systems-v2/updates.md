---
title: Skype ルームの Windows の更新プログラムを管理システム v2
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 10/10/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ''
description: Skype ルームの Windows の更新プログラムを管理システム v2
ms.openlocfilehash: 5765f99a247edcb6287878d4cda1154ec00782f4
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/13/2018
ms.locfileid: "26294168"
---
# <a name="manage-windows-updates"></a>Windows の更新プログラムを管理します。

Skype ルーム システム v2 (SRS v2) は、10 企業「IoT の Windows または Windows 10 エンタープライズ (VL) 上で実行され標準のデスクトップと同じ Windows の更新プログラムおよびオペレーティング システムのビルドを受信します。

Windows の更新プログラムは、いくつかの異なる方法で管理できます。

## <a name="hands-off-approach"></a>瞬時のアプローチ 
- 更新プログラムを自動的に Windows Update から直接ダウンロードし、業務時間外にインストールします。 変更が行われていない場合の構成にこれは、既定の状態です。
- 非遅延更新は、リリースの 1 日目を自動的にインストールされます。 
- 品質の更新プログラムとドライバーをダウンロードして自動的に 1 日 1 をインストールします。 
- 機能を更新します。 以下の追加の注記を参照してください。 

## <a name="windows-updates-for-businesshttpsdocsmicrosoftcomen-uswindowsdeploymentupdatewaas-manage-updates-wufb-gpo-or-intune"></a>[ビジネスのための Windows の更新プログラム](https://docs.microsoft.com/en-us/windows/deployment/update/waas-manage-updates-wufb)GPO (Intune)   
- KB の元のリリース日以降の遅延が構成されているのですが、WU または、WSUS から更新プログラムがダウンロードされます。 
- 複数の OU と組み合わせるか、これにより、作成するためのポリシーをフィルター処理「リング」、管理者が品質の更新プログラムを最初にインストールするデバイスを指定できますの配置となるものは後でインストールします。 信頼性とパフォーマンスの SCCM で Windows の更新プログラムを管理するオーバーヘッドを生じさせず展開全体で更新プログラムをロールアウトする前にシステムの一部をテストできます。
- WSUS とビジネスのための Windows の更新プログラムは、帯域幅の管理とビジネスのための Windows の更新プログラムのコントロールの両方を希望する場合は、[同時に構成されている](https://docs.microsoft.com/en-us/windows/deployment/update/waas-integrate-wufb)を提供します。
- 機能を更新します。 以下の追加の注記を参照してください。

## <a name="wsussccmhttpsdocsmicrosoftcomen-uswindowsdeploymentupdatewaas-manage-updates-configuration-manager"></a>[WSUS または SCCM](https://docs.microsoft.com/en-us/windows/deployment/update/waas-manage-updates-configuration-manager)
- ビジネスが「リング」または全体の展開内の特定の KB を対象とする追加オプションを使用して Windows の更新プログラムのような。 各更新プログラムは、個別に展開されたとは、テストではなく遅延のみで証明書利用者にあります。 
- 機能を更新します。 以下の追加の注記を参照してください。


### <a name="feature-updates"></a>機能の更新

品質と非 Deferable の更新プログラム、Windows の 10 とは異なり機能更新プログラム」(OS のメジャー リリース) は、Microsoft がテストして、SRS v2 を指定した更新プログラムの機能を評価した後のみインストールができます。 半年チャネル (または対象システムがテスト用には、そのチャネルに設定されている場合) にリリースするか、試行または構成によって手動でもプッシュは、たとえ、マイクロソフト側のブロックが解除されるまでインストールは許可がします。

SRS v2」の標準」を自動化された方法を使用しての Windows の更新プログラムをインストールまたは Windows の更新プログラムがあるため、デバイスを自動的に再起動ができません。 システムは可能性があります、ただし、更新プログラムをダウンロードし、それをインストールするのには次の再起動を待ちます。 手動で再起動誰かしない限り、インストールは自動の夜間の再起動時に発生します。 Windows の更新プログラムは、部屋に透過的でなければならない、UI は、Windows の更新プログラムによって中断されることはありませんする必要があります。

ドメインへの参加を選択した場合は、SCCM または WSUS を使用し、ポリシーまたはデバイスの更新プログラムをインストールするか、業務時間中に再起動を強制することにつながるアクションに特に注意が必要です。 システム展開の使用時に再起動するか、UI 上で Windows の更新プログラムに関する警告である場合は、する場合の構成を検討します。