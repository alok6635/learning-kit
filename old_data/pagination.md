
## pagination

#App.js-
import React, { useEffect, useState } from 'react'

const App = () => {
  const [data, setData] = useState([]);
  const [loading, setLoading] = useState(true);
  const [currentPage, setCurrentPage] = useState(1);
  const [postPerPage] = useState(5);


  useEffect(() => {
    const fetchData = async () => {
      try {
        const response = await fetch("https://jsonplaceholder.typicode.com/posts");
        const result = await response.json();
        setData(result);
        setLoading(false);
      } catch (err) {
        console.log(err)
      }
    }
    fetchData();
  }, [])

  // calculate pagination variable-
  const totalPosts = data.length;
  const totalPages = Math.ceil(totalPosts / postPerPage);
  const startIndex = (currentPage - 1) * postPerPage;
  const endIndex = startIndex + postPerPage;
  const currentData = data.slice(startIndex, endIndex);

const handlePreVpage=()=>{
    if(currentPage >1){
      setCurrentPage((prev)=> prev-1)
    }
}

const handleNextPage =()=>{
    if(currentPage < totalPages){
      setCurrentPage((prev)=> prev + 1)
    }
}

const handlepageClick=(pageNumber)=>{
            setCurrentPage(pageNumber)
}

  if (loading) {
    return (
      <p>Loading...... </p>
    )
  }
  return (
    <>
    <div className='app'>
      <ul>
        {
          currentData.map((item, index) => {
            return (
              <li key={index}>
                <h3>{item.title}</h3>
                <p>{item.body}</p>
              </li>
            )
          })
        }
      </ul>
      {/* pagination controls */}
      <div className='pagination'>
        <button className='arrow' id='prevPage' disabled={currentPage ===1} onClick={handlePreVpage}>
          ← <span className='nav_text'>PREV</span>
        </button>
        <div className='pages'>
          {Array.from({ length: totalPages }, (_, index) => (
            <div className={`page-number ${currentPage === index + 1 ? "active" : ""}`}
             onClick={()=>handlepageClick(index+1)}>{index + 1}</div>))}
        </div>
        <button className='arrow' id='nextPage' disabled={currentPage === totalPages} onClick={handleNextPage}>
          → <span className='nav_text'>NEXT</span>
        </button>
      </div>
    </div>

    </>
  )
}
export default App;

#index.css-
.app{
  width: 500px;
  margin: 0 auto 200px;
  padding: 0;
  text-align: center;
}
.app li{
  list-style: none;
  margin: 10px auto;
  padding: 12px;
  background: beige;
  border-radius: 10px;
}
.pagination{
  text-align: center;
  display: flex;
  text-align: center;
  justify-content: center;
}

.pages{
  display: flex;
  justify-content: space-between;
  align-items: center;
}
.page-number{
  cursor: pointer;
  background-color: azure;
  width: 30px;
  height: 30px;
  line-height: 10px;
  display: flex;
  align-items: center;
  justify-content: center;
  margin: 0 5px;
  transition: 0.4s ease;
}
.active{
  font: 1rem;
  height: 40px;
  width: 40px;
  background-color: blue;
}
button {
  display: flex;
  align-items: center;
  justify-content: space-between;
  border: none;
}
button:hover{
  background: antiquewhite;
}
button:disabled{
  cursor: not-allowed;
}
