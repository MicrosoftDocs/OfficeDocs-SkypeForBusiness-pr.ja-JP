---
title: グループ メンバーシップおよびベスト プラクティス アナライザーのユーザー権限
TOCTitle: グループ メンバーシップおよびベスト プラクティス アナライザーのユーザー権限
ms:assetid: f812e343-8f75-454e-b7a8-1b404e32071a
ms:mtpsurl: https://technet.microsoft.com/ja-jp/library/Gg591354(v=OCS.15)
ms:contentKeyID: 48274101
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# グループ メンバーシップおよびベスト プラクティス アナライザーのユーザー権限

 

_**トピックの最終更新日:** 2012-10-21_

ベスト プラクティス アナライザーを正常に実行するには、ログオンで使用したユーザー アカウントがローカル コンピューターの Administrators グループのメンバーである必要があります。また、環境をスキャンするには、ユーザー アカウントが次のグループのメンバーである必要があります。

  - **Domain Admins**   Active Directory Domain サービスの情報を列挙し、ドメイン コントローラーおよびグローバル カタログ サーバーの Windows Management Instrumentation (WMI) を呼び出すため。

  - **Administrators**   Windows Management Instrumentation (WMI) プロバイダーを呼び出してレジストリにアクセスするために、各 Lync Server 2013 内部コンピューターと各エッジ サーバーで必要。

  - **RTCUniversalReadOnlyAdmins**   完全または委任された読み取り専用の Lync Server 2013 管理者権限。

  - **Exchange View Only Administrator**   Microsoft Exchange 組織の完全または委任された Exchange View Only Administrator。

ユーザー アカウントで十分なユーザー権限がない場合、2 つのオプションがあります。

  - コマンド プロンプトで、**runas** コマンドを使って十分なユーザー権限があるアカウントからツールを実行します。構文は次のとおりです。
    
        runas /netonly /user:<domain>\<userName> rtcbpa.exe

  - \[**Active Directory に接続**\] ページで、ベスト プラクティス アナライザーの実行で使用する予定のアカウントの資格情報を設定します。\[**詳細ログイン オプションを表示**\] をクリックします。3 つのアカウントを入力できます。Active Directory Domain サービスに接続するアカウント、Lync Server 2013エッジ サーバー に接続するアカウント、および Exchange Server に接続するアカウントです。いずれかのアカウントを指定しなかった場合、ベスト プラクティス アナライザーのログオンと実行に使ったユーザー アカウントが使用されます。

