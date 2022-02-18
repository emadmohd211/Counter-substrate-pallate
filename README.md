# Counter-substrate-pallate
First i installed all the softwares and libraries required to run substrate framework on windows, which included visual studio build tools, windows 10 sdk. Then , installed rust, LLVM and Openssl after compiling it with cmake.<br/>
Then, i forked the substrate node template, and created a new pallet named counter inside pallet folder, copying the format of template pallet. <br/>
In order to integrate the new pallet with the runtime, i added it to the dependencies and features in cargo.toml in the runtime folder.<br/>
Then, in the counter pallet, inside file , lib.rs, i introduced hooks for blocknumber.Inside it, i used the `fn on_finalize(n: T::BlockNumber)` function, which is invoked when new block is added to the blockchain.<br/>
I also defined the storage value<br/>
`#[pallet::storage]
	#[pallet::getter(fn single_value)]
	pub(super) type SingleValue<T: Config> = StorageValue<_, u32, ValueQuery>;`<br/>
  that stores the counter after every 100 block is added to the blockchain.<br/>
  In order to compile the code, i executed `cargo build --release` from terminal.<br/>
  and in order to run the blockchain, in the bash terminal, i executed the command `./target/release/node-template --dev`<br/>
  The code file is located at,`\substrate-node-template\pallets\counter\src\lib.rs`.At line 70, is the code that implements the hook.<br/>
  It was my first time exploring this substrate framework and i am happy to have explored it. Thanks for it. <br/>
