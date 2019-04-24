---
title: リモート ユーザー アクセスの有効化または無効化
ms.reviewer: ''
ms:assetid: cd9d3ddc-4839-457a-86d9-b15413e74002
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182586(v=OCS.15)
ms:contentKeyID: 48185660
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: リモート ユーザーのリモート ユーザー アクセスを有効にした場合サポートされているリモート ユーザーは、インターネット経由で接続し、Skype を使用してビジネスのサーバーの内部のユーザーと共同作業するために VPN を使用して接続する必要はありません。
ms.openlocfilehash: aea136e6c8758fd646a20b8bc7a64a393d45a3e7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/23/2019
ms.locfileid: "32199928"
---
# <a name="enable-or-disable-remote-user-access-in-skype-for-business-server"></a>有効にするか、ビジネスのサーバーの Skype でのリモート ユーザー アクセスを無効にします。

リモート ユーザーは、組織内の永続的な Active Directory id を持つ、組織内のユーザーです。 リモート ユーザー多くの場合にサインイン Skype ビジネス サーバーからのネットワークの外部組織のネットワークに接続されていない場合、仮想プライベート ネットワーク (VPN) を使用しています。 リモート ユーザーには、在宅勤務の従業員が含まれます。 または、道と他のリモート作業者を信頼できるベンダーなどを与えられているエンタープライズ資格情報です。 リモート ユーザーのリモート ユーザー アクセスを有効にした場合サポートされているリモート ユーザーは、インターネット経由で接続し、Skype を使用してビジネスのサーバーの内部のユーザーと共同作業するために VPN を使用して接続する必要はありません。

リモート ユーザー アクセスをサポートするには、リモート ユーザー アクセスを有効にする必要があります。 リモート ユーザー アクセスを有効にすると、組織全体で有効です。 後で一時的または恒久的には、リモート ユーザー アクセスを防止する場合は、組織で無効にできます。 このセクションでを有効にするか、組織のリモート ユーザー アクセスを無効にする手順を使用します。


> [!NOTE]  
> アクセス エッジ サービスを実行しているサーバー、リモート ユーザーとの通信をサポートしていますでも構成するまで、リモート ユーザーがインスタント メッセージング (IM) または組織内の会議に参加できないリモート ユーザー アクセスを有効にすることのみを指定します。リモート ユーザー アクセスの使用を管理するために少なくとも 1 つのポリシーです。 Skype ビジネスのサーバーのポリシー設定が 1 つのポリシー レベルで適用されるは、別のポリシー レベルで適用される設定をオーバーライドできます。 ビジネス サーバー ポリシーの優先順位の Skype が: ユーザー ポリシー (ほとんどの影響) がサイト ポリシーを上書きし、[サイト ポリシーはグローバル ポリシー (最低限の影響) をよりも優先されます。 つまり、ポリシー設定が、そのポリシーの影響を受けるオブジェクトに近いほど、オブジェクトに及ぼす影響は大きくなります。 リモート ユーザー アクセスを使用するためのポリシーの構成に関する詳細については、 [Skype のビジネス サーバーでリモート ユーザー アクセスを制御するポリシーを構成する](../external-access-policies/configure-policies-to-control-remote-user-access.md)を参照してください。


## <a name="to-enable-or-disable-remote-user-access-for-your-organization"></a>有効にするか、組織のリモート ユーザー アクセスを無効にするには

1.  RTCUniversalServerAdmins グループ (または同等のユーザー権限を持つグループ) のメンバーであるユーザー アカウントまたは CsAdministrator の役割に割り当てられているユーザー アカウントから、内部展開の任意のコンピューターにログオンします。

2.  、ブラウザー ウィンドウを開き、を開くには、Skype ビジネス サーバーのコントロール パネルの管理 URL を入力します。 

3.  左側のナビゲーション バーで [**フェデレーションと外部アクセス**] をクリックし、[**アクセス エッジ構成**] をクリックします。

4.  [**アクセス エッジ構成**] ページで、[**グローバル**] をクリック**を編集**するには、、[**詳細の表示**] をクリックします。

5.  **アクセス エッジ構成の編集**] で、次のいずれかの操作を行います。
    
      - 組織のリモート ユーザー アクセスを有効にするには、**リモート ユーザー アクセスを有効にする**] チェック ボックスを選択します。
    
      - 組織のリモート ユーザー アクセスを無効にするには、**リモート ユーザー アクセスを有効にする**] チェック ボックスをオフにします。

6.  [**コミット**] をクリックします。

Skype をビジネスのサーバーを実行しているサーバーにサインインするのにはリモート ユーザーを有効にするには、リモート ユーザー アクセスをサポートするために少なくとも 1 つの外部アクセス ポリシーを構成することもあります。 詳細については、 [Skype のビジネス サーバーでリモート ユーザー アクセスを制御するポリシーを構成する](../external-access-policies/configure-policies-to-control-remote-user-access.md)を参照してください。


## <a name="enabling-or-disabling-remote-user-access-by-using-windows-powershell-cmdlets"></a>有効にするか、Windows PowerShell コマンドレットを使用して、リモート ユーザー アクセスを無効にします。

Windows PowerShell とセット CsAccessEdgeConfiguration コマンドレットを使用して、リモート ユーザー アクセスを管理できます。 ビジネス Server 2013 の管理シェルの Skype とは Windows PowerShell のリモート セッションからは、このコマンドレットを実行できます。 

## <a name="to-enable-remote-user-access"></a>リモート ユーザー アクセスを有効にするには

  - リモート ユーザー アクセスを有効にするには、 **AllowOutsideUsers**プロパティの値を True ($True) に設定します。
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $True

## <a name="to-disable-remote-user-access"></a>リモート ユーザー アクセスを無効にするには

  - リモート ユーザー アクセスを無効にするには、 **AllowOutsideUsers**プロパティの値を False ($False) に設定します。
    
        Set-CsAccessEdgeConfiguration -AllowOutsideUsers $False


