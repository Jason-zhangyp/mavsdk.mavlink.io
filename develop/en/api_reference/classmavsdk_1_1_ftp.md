# mavsdk::Ftp Class Reference
`#include: ftp.h`

----


Implements file transfer functionality using MAVLink FTP. 


## Data Structures


struct [ProgressData](structmavsdk_1_1_ftp_1_1_progress_data.md)

## Public Types


Type | Description
--- | ---
enum [Result](#classmavsdk_1_1_ftp_1a4cc4f42a3ef6d63403d811e594b946e4) | Possible results returned for FTP commands.
std::function< void([Result](classmavsdk_1_1_ftp.md#classmavsdk_1_1_ftp_1a4cc4f42a3ef6d63403d811e594b946e4))> [ResultCallback](#classmavsdk_1_1_ftp_1a04a12a1ab954b24a54570300f89486b0) | Callback type for asynchronous [Ftp](classmavsdk_1_1_ftp.md) calls.
std::function< void([Ftp::Result](classmavsdk_1_1_ftp.md#classmavsdk_1_1_ftp_1a4cc4f42a3ef6d63403d811e594b946e4), [ProgressData](structmavsdk_1_1_ftp_1_1_progress_data.md))> [DownloadCallback](#classmavsdk_1_1_ftp_1aa1f79399f168f386610b5a8f3e7c75d4) | Callback type for download_async.
std::function< void([Ftp::Result](classmavsdk_1_1_ftp.md#classmavsdk_1_1_ftp_1a4cc4f42a3ef6d63403d811e594b946e4), [ProgressData](structmavsdk_1_1_ftp_1_1_progress_data.md))> [UploadCallback](#classmavsdk_1_1_ftp_1a8b8d4d8e6f9efe96e6c5feb38fae9ff4) | Callback type for upload_async.
std::function< void([Result](classmavsdk_1_1_ftp.md#classmavsdk_1_1_ftp_1a4cc4f42a3ef6d63403d811e594b946e4), std::vector< std::string >)> [ListDirectoryCallback](#classmavsdk_1_1_ftp_1a87a77c4e013a8665017504a550d876b7) | Callback type for list_directory_async.
std::function< void([Result](classmavsdk_1_1_ftp.md#classmavsdk_1_1_ftp_1a4cc4f42a3ef6d63403d811e594b946e4), bool)> [AreFilesIdenticalCallback](#classmavsdk_1_1_ftp_1abe24e99f7141a234206f8952d2f61318) | Callback type for are_files_identical_async.

## Public Member Functions


Type | Name | Description
---: | --- | ---
&nbsp; | [Ftp](#classmavsdk_1_1_ftp_1ad0b5909e631746c1dd5e2151c727e67f) ([System](classmavsdk_1_1_system.md) & system) | Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).
&nbsp; | [~Ftp](#classmavsdk_1_1_ftp_1a10f8eff234be8dcaca8f40482e744ee6) () | Destructor (internal use only).
&nbsp; | [Ftp](#classmavsdk_1_1_ftp_1a22af5baed783408c9599af6303b3e862) (const [Ftp](classmavsdk_1_1_ftp.md) &)=delete | Copy constructor (object is not copyable).
void | [reset_async](#classmavsdk_1_1_ftp_1aab8895023bb3db8750622a5a38adcf07) (const [ResultCallback](classmavsdk_1_1_ftp.md#classmavsdk_1_1_ftp_1a04a12a1ab954b24a54570300f89486b0) callback) | Resets FTP server in case there are stale open sessions.
void | [download_async](#classmavsdk_1_1_ftp_1afd01f6380b2a5d4b433abaf7aa734fc0) (std::string remote_file_path, std::string local_dir, [DownloadCallback](classmavsdk_1_1_ftp.md#classmavsdk_1_1_ftp_1aa1f79399f168f386610b5a8f3e7c75d4) callback) | Downloads a file to local directory.
void | [upload_async](#classmavsdk_1_1_ftp_1a14489e59f195709915d01ad093790b09) (std::string local_file_path, std::string remote_dir, [UploadCallback](classmavsdk_1_1_ftp.md#classmavsdk_1_1_ftp_1a8b8d4d8e6f9efe96e6c5feb38fae9ff4) callback) | Uploads local file to remote directory.
void | [list_directory_async](#classmavsdk_1_1_ftp_1abf5d83104a7293413b62e7a8ba1a0f2c) (std::string remote_dir, const [ListDirectoryCallback](classmavsdk_1_1_ftp.md#classmavsdk_1_1_ftp_1a87a77c4e013a8665017504a550d876b7) callback) | Lists items from a remote directory.
void | [create_directory_async](#classmavsdk_1_1_ftp_1aa53fdd5c005bd4da3e0cb29d448689d3) (std::string remote_dir, const [ResultCallback](classmavsdk_1_1_ftp.md#classmavsdk_1_1_ftp_1a04a12a1ab954b24a54570300f89486b0) callback) | Creates a remote directory.
void | [remove_directory_async](#classmavsdk_1_1_ftp_1a25823c7298dc2d081532dd094d013b8a) (std::string remote_dir, const [ResultCallback](classmavsdk_1_1_ftp.md#classmavsdk_1_1_ftp_1a04a12a1ab954b24a54570300f89486b0) callback) | Removes a remote directory.
void | [remove_file_async](#classmavsdk_1_1_ftp_1a3ecda69288fb860a8da1f8fad25af31c) (std::string remote_file_path, const [ResultCallback](classmavsdk_1_1_ftp.md#classmavsdk_1_1_ftp_1a04a12a1ab954b24a54570300f89486b0) callback) | Removes a remote file.
void | [rename_async](#classmavsdk_1_1_ftp_1afea8b15ad7b5748b0b5f68fd7103514a) (std::string remote_from_path, std::string remote_to_path, const [ResultCallback](classmavsdk_1_1_ftp.md#classmavsdk_1_1_ftp_1a04a12a1ab954b24a54570300f89486b0) callback) | Renames a remote file or remote directory.
void | [are_files_identical_async](#classmavsdk_1_1_ftp_1abddebf1a103b2853116e68f5f870e4a7) (std::string local_file_path, std::string remote_file_path, const [AreFilesIdenticalCallback](classmavsdk_1_1_ftp.md#classmavsdk_1_1_ftp_1abe24e99f7141a234206f8952d2f61318) callback) | Compares a local file to a remote file using a CRC32 checksum.
[Result](classmavsdk_1_1_ftp.md#classmavsdk_1_1_ftp_1a4cc4f42a3ef6d63403d811e594b946e4) | [set_root_directory](#classmavsdk_1_1_ftp_1a77dab408f90158a7cd0ade86d16108eb) (std::string root_dir)const | Set root directory for MAVLink FTP server.
[Result](classmavsdk_1_1_ftp.md#classmavsdk_1_1_ftp_1a4cc4f42a3ef6d63403d811e594b946e4) | [set_target_component_id](#classmavsdk_1_1_ftp_1af8016be51a1916f4991ff1e528c372dc) (uint32_t component_id)const | Set target component ID. By default it is the autopilot.
uint32_t | [get_our_component_id](#classmavsdk_1_1_ftp_1a29af1a480135d19c3bce237e340e8df5) () const | Get our own component ID.
const [Ftp](classmavsdk_1_1_ftp.md) & | [operator=](#classmavsdk_1_1_ftp_1a01dc5f41d1e684a667d31c213728b376) (const [Ftp](classmavsdk_1_1_ftp.md) &)=delete | Equality operator (object is not copyable).


## Constructor & Destructor Documentation


### Ftp() {#classmavsdk_1_1_ftp_1ad0b5909e631746c1dd5e2151c727e67f}
```cpp
mavsdk::Ftp::Ftp(System &system)
```


Constructor. Creates the plugin for a specific [System](classmavsdk_1_1_system.md).

The plugin is typically created as shown below: 

```cpp
auto ftp = std::make_shared<Ftp>(system);
```

**Parameters**

* [System](classmavsdk_1_1_system.md)& **system** - The specific system associated with this plugin.

### ~Ftp() {#classmavsdk_1_1_ftp_1a10f8eff234be8dcaca8f40482e744ee6}
```cpp
mavsdk::Ftp::~Ftp()
```


Destructor (internal use only).


### Ftp() {#classmavsdk_1_1_ftp_1a22af5baed783408c9599af6303b3e862}
```cpp
mavsdk::Ftp::Ftp(const Ftp &)=delete
```


Copy constructor (object is not copyable).


**Parameters**

* const [Ftp](classmavsdk_1_1_ftp.md)&  - 

## Member Typdef Documentation


### typedef ResultCallback {#classmavsdk_1_1_ftp_1a04a12a1ab954b24a54570300f89486b0}

```cpp
using mavsdk::Ftp::ResultCallback =  std::function<void(Result)>
```


Callback type for asynchronous [Ftp](classmavsdk_1_1_ftp.md) calls.


### typedef DownloadCallback {#classmavsdk_1_1_ftp_1aa1f79399f168f386610b5a8f3e7c75d4}

```cpp
using mavsdk::Ftp::DownloadCallback =  std::function<void(Ftp::Result, ProgressData)>
```


Callback type for download_async.


### typedef UploadCallback {#classmavsdk_1_1_ftp_1a8b8d4d8e6f9efe96e6c5feb38fae9ff4}

```cpp
using mavsdk::Ftp::UploadCallback =  std::function<void(Ftp::Result, ProgressData)>
```


Callback type for upload_async.


### typedef ListDirectoryCallback {#classmavsdk_1_1_ftp_1a87a77c4e013a8665017504a550d876b7}

```cpp
using mavsdk::Ftp::ListDirectoryCallback =  std::function<void(Result, std::vector<std::string>)>
```


Callback type for list_directory_async.


### typedef AreFilesIdenticalCallback {#classmavsdk_1_1_ftp_1abe24e99f7141a234206f8952d2f61318}

```cpp
using mavsdk::Ftp::AreFilesIdenticalCallback =  std::function<void(Result, bool)>
```


Callback type for are_files_identical_async.


## Member Enumeration Documentation


### enum Result {#classmavsdk_1_1_ftp_1a4cc4f42a3ef6d63403d811e594b946e4}


Possible results returned for FTP commands.


Value | Description
--- | ---
<span id="classmavsdk_1_1_ftp_1a4cc4f42a3ef6d63403d811e594b946e4a88183b946cc5f0e8c96b2e66e1c74a7e"></span> `Unknown` | Unknown result. 
<span id="classmavsdk_1_1_ftp_1a4cc4f42a3ef6d63403d811e594b946e4a505a83f220c02df2f85c3810cd9ceb38"></span> `Success` | Success. 
<span id="classmavsdk_1_1_ftp_1a4cc4f42a3ef6d63403d811e594b946e4a10ac3d04253ef7e1ddc73e6091c0cd55"></span> `Next` | Intermediate message showing progress. 
<span id="classmavsdk_1_1_ftp_1a4cc4f42a3ef6d63403d811e594b946e4ac85a251cc457840f1e032f1b733e9398"></span> `Timeout` | Timeout. 
<span id="classmavsdk_1_1_ftp_1a4cc4f42a3ef6d63403d811e594b946e4ad8a942ef2b04672adfafef0ad817a407"></span> `Busy` | Operation is already in progress. 
<span id="classmavsdk_1_1_ftp_1a4cc4f42a3ef6d63403d811e594b946e4a1d9fef8a4733b0ea18ff683be51fc196"></span> `FileIoError` | File IO operation error. 
<span id="classmavsdk_1_1_ftp_1a4cc4f42a3ef6d63403d811e594b946e4aea1776502570f06ddc0569c079cb9ee2"></span> `FileExists` | File exists already. 
<span id="classmavsdk_1_1_ftp_1a4cc4f42a3ef6d63403d811e594b946e4aab7e9f2fa8b2404bc25061dd572e9797"></span> `FileDoesNotExist` | File does not exist. 
<span id="classmavsdk_1_1_ftp_1a4cc4f42a3ef6d63403d811e594b946e4a07b15a02a7ed4e09d46ea06d10d0e0cd"></span> `FileProtected` | File is write protected. 
<span id="classmavsdk_1_1_ftp_1a4cc4f42a3ef6d63403d811e594b946e4a627251310d3384b591e4138be21145d5"></span> `InvalidParameter` | Invalid parameter. 
<span id="classmavsdk_1_1_ftp_1a4cc4f42a3ef6d63403d811e594b946e4ab4080bdf74febf04d578ff105cce9d3f"></span> `Unsupported` | Unsupported command. 
<span id="classmavsdk_1_1_ftp_1a4cc4f42a3ef6d63403d811e594b946e4aca3da8f495e4e628912a7798655da6c2"></span> `ProtocolError` | General protocol error. 

## Member Function Documentation


### reset_async() {#classmavsdk_1_1_ftp_1aab8895023bb3db8750622a5a38adcf07}
```cpp
void mavsdk::Ftp::reset_async(const ResultCallback callback)
```


Resets FTP server in case there are stale open sessions.

This function is non-blocking.

**Parameters**

* const [ResultCallback](classmavsdk_1_1_ftp.md#classmavsdk_1_1_ftp_1a04a12a1ab954b24a54570300f89486b0) **callback** - 

### download_async() {#classmavsdk_1_1_ftp_1afd01f6380b2a5d4b433abaf7aa734fc0}
```cpp
void mavsdk::Ftp::download_async(std::string remote_file_path, std::string local_dir, DownloadCallback callback)
```


Downloads a file to local directory.


**Parameters**

* std::string **remote_file_path** - 
* std::string **local_dir** - 
* [DownloadCallback](classmavsdk_1_1_ftp.md#classmavsdk_1_1_ftp_1aa1f79399f168f386610b5a8f3e7c75d4) **callback** - 

### upload_async() {#classmavsdk_1_1_ftp_1a14489e59f195709915d01ad093790b09}
```cpp
void mavsdk::Ftp::upload_async(std::string local_file_path, std::string remote_dir, UploadCallback callback)
```


Uploads local file to remote directory.


**Parameters**

* std::string **local_file_path** - 
* std::string **remote_dir** - 
* [UploadCallback](classmavsdk_1_1_ftp.md#classmavsdk_1_1_ftp_1a8b8d4d8e6f9efe96e6c5feb38fae9ff4) **callback** - 

### list_directory_async() {#classmavsdk_1_1_ftp_1abf5d83104a7293413b62e7a8ba1a0f2c}
```cpp
void mavsdk::Ftp::list_directory_async(std::string remote_dir, const ListDirectoryCallback callback)
```


Lists items from a remote directory.

This function is non-blocking.

**Parameters**

* std::string **remote_dir** - 
* const [ListDirectoryCallback](classmavsdk_1_1_ftp.md#classmavsdk_1_1_ftp_1a87a77c4e013a8665017504a550d876b7) **callback** - 

### create_directory_async() {#classmavsdk_1_1_ftp_1aa53fdd5c005bd4da3e0cb29d448689d3}
```cpp
void mavsdk::Ftp::create_directory_async(std::string remote_dir, const ResultCallback callback)
```


Creates a remote directory.

This function is non-blocking.

**Parameters**

* std::string **remote_dir** - 
* const [ResultCallback](classmavsdk_1_1_ftp.md#classmavsdk_1_1_ftp_1a04a12a1ab954b24a54570300f89486b0) **callback** - 

### remove_directory_async() {#classmavsdk_1_1_ftp_1a25823c7298dc2d081532dd094d013b8a}
```cpp
void mavsdk::Ftp::remove_directory_async(std::string remote_dir, const ResultCallback callback)
```


Removes a remote directory.

This function is non-blocking.

**Parameters**

* std::string **remote_dir** - 
* const [ResultCallback](classmavsdk_1_1_ftp.md#classmavsdk_1_1_ftp_1a04a12a1ab954b24a54570300f89486b0) **callback** - 

### remove_file_async() {#classmavsdk_1_1_ftp_1a3ecda69288fb860a8da1f8fad25af31c}
```cpp
void mavsdk::Ftp::remove_file_async(std::string remote_file_path, const ResultCallback callback)
```


Removes a remote file.

This function is non-blocking.

**Parameters**

* std::string **remote_file_path** - 
* const [ResultCallback](classmavsdk_1_1_ftp.md#classmavsdk_1_1_ftp_1a04a12a1ab954b24a54570300f89486b0) **callback** - 

### rename_async() {#classmavsdk_1_1_ftp_1afea8b15ad7b5748b0b5f68fd7103514a}
```cpp
void mavsdk::Ftp::rename_async(std::string remote_from_path, std::string remote_to_path, const ResultCallback callback)
```


Renames a remote file or remote directory.

This function is non-blocking.

**Parameters**

* std::string **remote_from_path** - 
* std::string **remote_to_path** - 
* const [ResultCallback](classmavsdk_1_1_ftp.md#classmavsdk_1_1_ftp_1a04a12a1ab954b24a54570300f89486b0) **callback** - 

### are_files_identical_async() {#classmavsdk_1_1_ftp_1abddebf1a103b2853116e68f5f870e4a7}
```cpp
void mavsdk::Ftp::are_files_identical_async(std::string local_file_path, std::string remote_file_path, const AreFilesIdenticalCallback callback)
```


Compares a local file to a remote file using a CRC32 checksum.

This function is non-blocking.

**Parameters**

* std::string **local_file_path** - 
* std::string **remote_file_path** - 
* const [AreFilesIdenticalCallback](classmavsdk_1_1_ftp.md#classmavsdk_1_1_ftp_1abe24e99f7141a234206f8952d2f61318) **callback** - 

### set_root_directory() {#classmavsdk_1_1_ftp_1a77dab408f90158a7cd0ade86d16108eb}
```cpp
Result mavsdk::Ftp::set_root_directory(std::string root_dir) const
```


Set root directory for MAVLink FTP server.

This function is blocking.

**Parameters**

* std::string **root_dir** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_ftp.md#classmavsdk_1_1_ftp_1a4cc4f42a3ef6d63403d811e594b946e4) - Result of request.

### set_target_component_id() {#classmavsdk_1_1_ftp_1af8016be51a1916f4991ff1e528c372dc}
```cpp
Result mavsdk::Ftp::set_target_component_id(uint32_t component_id) const
```


Set target component ID. By default it is the autopilot.

This function is blocking.

**Parameters**

* uint32_t **component_id** - 

**Returns**

&emsp;[Result](classmavsdk_1_1_ftp.md#classmavsdk_1_1_ftp_1a4cc4f42a3ef6d63403d811e594b946e4) - Result of request.

### get_our_component_id() {#classmavsdk_1_1_ftp_1a29af1a480135d19c3bce237e340e8df5}
```cpp
uint32_t mavsdk::Ftp::get_our_component_id() const
```


Get our own component ID.

This function is blocking.

**Returns**

&emsp;uint32_t - Result of request.

### operator=() {#classmavsdk_1_1_ftp_1a01dc5f41d1e684a667d31c213728b376}
```cpp
const Ftp& mavsdk::Ftp::operator=(const Ftp &)=delete
```


Equality operator (object is not copyable).


**Parameters**

* const [Ftp](classmavsdk_1_1_ftp.md)&  - 

**Returns**

&emsp;const [Ftp](classmavsdk_1_1_ftp.md) & - 